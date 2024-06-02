# UiBak 模板

>
> Demo 图片存储在七牛云的，空间名为 uibak, 资源路径： http://demo-assets.uibak.com/themesdev/xxx.png

## 网站架构介绍

|-- index
  |-- collection
    |-- collection_section
      |-- page
        |-- code
  |-- support
    |-- support_section
      |- post
  |-- blog
    |-- post

集合是一个分类，集合下面是页面模板或者块模板，创建集合的时候，通过 is_block 属性来判断页面是展示 Page列表、还是 code 预览图

创建collection 集合的时候，选择是否是 block 模板（否则是 page 模板），两者的区别：
* page 类型集合首先是显示页面列表，再进入页面详情
* block 类型集合在集合页面就直接列举展示出了所有的模板
* page 和 block 模板下面，都有且必须创建一个 code 子页面，用于保持模板原始的 HTML

帮助中心
support > support_section > post

博客
blog > post

提示： 将“博客”和“帮助中心”选择“不在导航中显示”和“不在列表中显示”

## 如何搬运 themes.dev 上面的模板

| https://www.themes.dev/

1. 下载 themes.dev 上面的模板源文件到本地
2. 上传 images 目录中的文件到七牛云空间 uibak/themesdev/ 目录下
3. vscode 打开模板，批量替换掉 blocks/ 下面的文件引用图片的方式
    >  src="../../images/([^"]+)"  =>  src="http://demo-assets.uibak.com/themesdev/$1"
    最终本地的文件 images/user.jpg 就变成了地址： http://demo-assets.uibak.com/themesdev/user.jpg

  注意：上面代码替换了 blocks 下面的原始 Raw 内容，但是没有替换掉”Copy"动作复制的内容，所以要进行下一步

4. vscode 批量替换掉 collections 下面的文件引用路径：
    > src=&#34;\/images\/([^&"]+)&#34;   => src=&#34;http://demo-assets.uibak.com/themesdev/$1&#34;

5. 浏览器打开 collections 下面的 HTML 文件，即可点击“Copy"复制相关代码到 UIBak.com 后台了


## UIBak 准备填充的内容结构
｜ 参考 themes.dev 和 tailwindui.com

-- UI components (themes.dev)
  Accordion
  Alert
  Avatar
  Badge
  Breadcrumb
  Button
  Button Group
  Card
  Divider
  Dropdown
  Layout
  List
  Media Object
  Modal
  Notification
  Pagination
  Progress
  Tab
  Table
  Tooltip

-- Page sections (themes.dev)
  Hero Sections
  Feature Sections
  CTA Sections
  Pricing Sections
  Header Sections
  Newsletter Sections
  Stats
  Testimonials
  Blog Sections
  Contact Sections
  Team Sections
  Content Sections
  Logo Clouds
  FAQs
  Footers

-- Page elements (同上面合并)
  Header
  Menu
  Banner
  Forms
  Grids
  Modals
  Navigations
  Containers
  Panels
  List containers
  Media Objects
  Dividers

-- Documentation page templates
  *
  index
  list
  nav_tree
  feedback

-- Landing page templates
  app
  consultancy
  course
  meeting
  minimal
  saas
  services
  tech

-- Portal page templates
  404
  aboutus
  article
  blog
  changelog
  contact
  feature
  homepage
  modal
  pricing
  sidebar-menu
  signin
  support-article
  support-overview

-- Ecommerce page templates
  Product Overviews
  Product Lists
  Storefront Pages
  Product Pages
  Category Pages
  Shopping Cart Pages
  Checkout Pages
  Order Detail Pages



