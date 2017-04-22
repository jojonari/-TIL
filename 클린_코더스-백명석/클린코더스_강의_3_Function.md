클린 코더스 강의 3. Function
=============================
1. 원칙
  * 한가지 일만 해야 한다.
  * 함수의 크기는 작아야한다.
  * 잘 지어진 서술적인 긴 이름을 갖는 많은/작은 함수들로 유지해야 한다.

2. The First Rule of Functions
  * 더이상 작아질 수 없을 만큼 작아야한다.
  * 큰 함수를 보면 클래스로 추출할 생가을 해야한다.
  * 클래스는 일련의 변수들에 동작하는 기능의 집합이다.

3. 개선
  * 읽기 쉬워지고
  * 이해하기 쉬워지고
  * 함수가 자신의 의돌ㄹ 잘 전달한다.

4. 개선의 원인
  * Small
    - 함수의 첫번째 규칙
    - 함수는 작아질 수 있는 한 최대한 작아야 한다.
  * 블록이 적어야 한다.
    - if, else, while 문장 등의 내부 블록은 한줄이어야 한다.
      - 괄호가 없어야 한다.
      - 함수 호출이어야 한다.
  * Indenting이 적어야 한다.
    - 함수는 중첩 구조를 갖을 만큼 크면 안된다.
    - 들여쓰기는 한 두 단계 정도만 사용

5. Functions should do one thing
  * 리펙토링 후 메소드는 한가지 일만 한다.
  * 함수의 각 스텝들은 함수 이름보다 한 수준 낮은 추상화 수준을 갖는다.
  * 함수가 수행하는 모든 일의 추상화 수준이 같다.
  * 함수의 각 스텝들이 함수 이름이 갖는 추상화 수준보다 한 단계 낮은 것으로만 이뤄졌다면 함수는 한가지 일만 하는 것
  * 한 가지 일만 하도록 하는 것
   - 원래코드는 추상화 수준이 다른 많은 단계들을 포함하므로 한가지 이상의 일을 한다는 것이 명확
   - 하지만 의미있게 최종적으로 줄이는 것이 어렵다.
   - 함수가 하나 이상의 일을 한다고 말할 수 있는 경우
   - 단순한 구현의 재인용이 아닌 이름으로 함수를 추출할 수 있을 때

7. 마무리
  * 큰함수
    - 변수와 인자들을 가짐
    - 들여쓰기가 존재하고 변소들을 사용해서 통신하는 기능들의 집합
    - 하나이상의 클래스로 분리 할 수 있다.

Intelli J
---------
* extract method Object : 메소드를 클래스로 추출
* variable : 변수로 추출

> 리팩토링 예제 
<pre><code>
// 리펙토링 후
public class FitnessExample {
    public String testableHtml(PageData pageData, boolean includeSuiteSetup) throws Exception {
        return new TestalbeHtmlBuilder(pageData, includeSuiteSetup).invoke();
    }

    private class TestalbeHtmlBuilder {
        private PageData pageData;
        private boolean includeSuiteSetup;
        private WikiPage wikiPage;
        private StringBuffer buffer;

        public TestalbeHtmlBuilder(PageData pageData, boolean includeSuiteSetup) {
            this.pageData = pageData;
            this.includeSuiteSetup = includeSuiteSetup;
            this.wikiPage = pageData.getWikiPage();
            this.buffer = new StringBuffer();
        }

        public String invoke() throws Exception {

            if (isTestPage()) {
                includeSetup();
                buffer.append(pageData.getContent());
                includeTearDown();
            }

            pageData.setContent(buffer.toString());
            return pageData.getHtml();
        }

        private boolean isTestPage() throws Exception {
            return pageData.hasAttribute("Test");
        }

        private void includeTearDown() throws Exception {
            includeInherited("TearDown", "teardown");
            if (includeSuiteSetup) {
                includeInherited(SuiteResponder.SUITE_TEARDOWN_NAME, "teardown");
            }
        }

        private void includeSetup() throws Exception {
            if (includeSuiteSetup) {
                includeInherited(SuiteResponder.SUITE_SETUP_NAME, "setup");
            }
            includeInherited("SetUp", "setup");
        }

        private void includeInherited(String pageName, String mode) throws Exception {
            WikiPage suiteSetup = PageCrawlerImpl.getInheritedPage(pageName, wikiPage);
            if (suiteSetup != null) {
                includePage(suiteSetup, mode);
            }
        }

        private void includePage(WikiPage suiteSetup, String mode) throws Exception {
            WikiPagePath pagePath = wikiPage.getPageCrawler().getFullPath(suiteSetup);
            String pagePathName = PathParser.render(pagePath);
            buffer.append("!include -" + mode + " .").append(pagePathName).append("\n");
        }
    }
</code></pre>
