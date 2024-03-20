# JavaFx-PaginationPicker-Release
JavaFx-PaginationPicker Release

# JavaFx-PaginationPicker By WangZhiYou
- javaFx customizationDate Pagination，support page control！
- javaFx 自定义时间选择组件 Pagination， javaFx 源代码分页功能较少，该代码组件支持首页、上一页、下一页、尾页、跳转、每页数量等操作，同时展示总数据量！
- 效果如下图所示：

  ![image](static/1.gif)
- 将jar包引用到自己项目中

  jar包下载地址：

- 使用方式一（fxml引用）： 

    ```
      <PaginationPicker>
         <VBox.margin>
            <Insets bottom="6.0" left="6.0" right="6.0" top="6.0" />
         </VBox.margin>
      </PaginationPicker>
    ```
  
- 使用方式二（Stage实现）：
     ```
  public class PaginationPickerTest extends Application {
      @Override
      public void start(Stage primaryStage) throws Exception {
          //初始化一个分页
          PaginationPicker paginationPicker = new PaginationPicker();
  
          paginationPicker.setTotal(30);//设置总数据量，默认0
          paginationPicker.setPageSize(30);//设置每页显示条数，默认30
          paginationPicker.setPageButtonCount(9);//设置页码按钮的数量，默认7，当总页数超过该值时会折叠，大于等于 5 且小于等于 21 的奇数
          paginationPicker.setCurrentPage(3);//设置当前选择页码，默认第一页（注意：必须放在所有设置条件之后）。不小于0 并且 不大于总页数
          paginationPicker.setPaginationButtonFontSize(12);//设置分页字体大小，默认10(不小于2)
  
          //监听点击动作事件
          paginationPicker.setOnAction(new EventHandler<ActionEvent>() {
              @Override
              public void handle(ActionEvent event) {
                  System.out.println("当前选择页码："+paginationPicker.getCurrentPage());
              }
          });
  
          //设置一个容器
          final VBox vBox = new VBox();
          vBox.setPrefHeight(200);
          vBox.setPrefWidth(950);
          vBox.setStyle("-fx-padding: 50px 0px 0px 0px;");
          vBox.getChildren().add(paginationPicker);
  
          final Scene scene = new Scene(vBox);
          primaryStage.setScene(scene);
          primaryStage.sizeToScene();
          primaryStage.show();
  
      }
      public static void main(String[] args) {
          launch(args);
      }
  }
  ```


## 参数说明

  | 函数   | 说明  | 类型      | 可选值                 | 默认值 |
  |------|-----|---------|---------------------|-----|
  | setPageSize | 设置每页显示条目个数 | Integer | 不小于1                | 30  |
  | setTotal | 设置总条目数量 | Integer | 不小于0                | 0   |
  | setPageButtonCount | 设置页码按钮的数量，当总页数超过该值时会折叠 | Integer | 大于等于 5 且小于等于 21 的奇数 | 7   |
  | setCurrentPage | 设置当前选择页码，默认第一页（注意：必须放在所有设置条件之后） | Integer | 不小于0 并且 不大于总页数      | 1   |
  | getPageSize | 获取每页显示条目个数 | — | —                   | 30  |
  | getTotal | 获取总条目数量 | — | —                   | 0   |
  | getPageCount | 获取总页数 | — | —                   | 0   |
  | getPageButtonCount | 获取页码按钮的数量 | — | —                   | 7   |
  | getCurrentPage | 获取当前选中页码 | — | —                   | 0   |
  | setPaginationButtonFontSize | 设置分页字体大小    | Integer | 不小于2               | 10  |



# 一、更新记录
- 【0.0.1】 2024-03-20

  1、【初始化】初始化提交，自定义分页组件，支持 首页、上一页、下一页、尾页、跳转等功能
