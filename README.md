# SpringBoot (SpringMVC/Thymeleaf) BootCamp

## Projectの作成

+ https://start.spring.io/
でWeb/Thymeleafを選択する
+ https://github.com/karmickoala/springboot-bootcamp-20161214
のBootCampを実行する
+ STS(Spring Tool Suite)のNew Spring Starter Projectで作成（Web/Thymeleaf）

のいずれかで、SpringMVC/Thymeleafを利用できるようにする。

+ spring-boot-starter-web
+ spring-boot-starter-thymeleaf

が依存関係に含まれていればOKです。

## Controllerの作成

+ クラスを追加します。

この時に自動生成されている、Applicationクラスと同じかあるいは階層として下のパッケージに格納してください。
Springが起動時にデフォルトで自分自身よりも下の階層のクラスを走査して、コンポーネントをみつけます。

```
@Controller
public class SubjectController {

     @RequestMapping("/index")
     public ModelAndView index(){
          ModelAndView view = new ModelAndView();

          view.addObject("name", "アイウエオ");

          view.setViewName("test");

          return view;
     }

}
```

+ アノテーションの説明

@Controller
SpringMVCで取り扱うアノテーション

@RequestMapping("/index")
画面遷移へのURLマッピングを記載するアノテーション

+ 画面を作成する
クラスパス配下のtemplatesディレクトリにThymeleafのテンプレートをおきます。
上記のsetView("test")となっているので、test.htmlとして作成します。

通常のHTML（metaタグが閉じられているか確認）に以下の項目を追加してみましょう。

```
<h1>テスト</h1>
  <h3 th:text="${name}"></h3>
```

Thymeleafの使い方は
http://www.thymeleaf.org/doc/tutorials/2.1/usingthymeleaf_ja.html
を参照してください。

