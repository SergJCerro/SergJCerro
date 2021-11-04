    <script src="https://cdnjs.cloudflare.com/ajax/libs/vue/2.1.10/vue.min.js"></script>
    <script id="rendered-js">
      class Post {
        constructor(name, level) {
          (this.name = name),
            (this.level = level)
        }
      }
      class Info{
          constructor(greeting,fname,age,phrase,country,endgreeting){
          (this.greeting = greeting),
          (this.fname = fname),
          (this.age = age),
          (this.phrase = phrase),
          (this.country = country),
          (this.endgreeting = endgreeting)
          }
      }
      class Pro{
          constructor(title,img){
              (this.title = title),
              (this.img = img)
          }
      }
      const app = new Vue({
        el: "#app",
        data: {
          keyword: "",
          onOff: true,
          basicInfo :[
              new Info("Hello! My Name is ",
              "Sergio J Cerritos.","I am 21 Years Old",
              "I am From the Beatuiful Country Of ",
              "Belize", "Pleasure In meeting your Acquaintance")
          ],
          languageList: [
            new Post("Spanish", "C2"),
            new Post("English", "C2"),
            new Post("Deutsch", "A2")
          ],
          programmingLanguages : [
              new Pro("HTML","https://cdn.glitch.me/490b58bc-729d-43e4-a08d-ea0ab35ecdf2%2Ffile_type_html_icon_130541.png?v=1635998842040"),
              new Pro("CSS","https://cdn.glitch.me/490b58bc-729d-43e4-a08d-ea0ab35ecdf2%2FCSS3_icon-icons.com_67069.png?v=1635998849500"),
              new Pro("JS","https://cdn.glitch.me/490b58bc-729d-43e4-a08d-ea0ab35ecdf2%2Ffile_type_js_official_icon_130509.png?v=1635998853862"),
              new Pro("Wordpress","https://cdn.glitch.me/490b58bc-729d-43e4-a08d-ea0ab35ecdf2%2Fwordpress_icon-icons.com_60472.png?v=1635999036434")
          ]
        },
        methods: {
          toggleOnOff() {
            this.onOff = !this.onOff;
          },
        },

        computed: {
          languagesList() {
            return this.languageList.filter((post) =>
              post.name.toLowerCase().includes(this.keyword)
            );
          },
          infoList(){
              return this.basicInfo.filter((info) =>
              info.name.toLowerCase().includes(this.keyword)
              );
          },
          proList(){
              return this.programmingLanguages.filter((pro) =>
              pro.name.toLowerCase().includes(this.keyword))

          }
        },
      });
    </script>
