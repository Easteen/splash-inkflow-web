# Vue 3 + TypeScript + Vite

This template should help get you started developing with Vue 3 and TypeScript in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

Learn more about the recommended Project Setup and IDE Support in the [Vue Docs TypeScript Guide](https://vuejs.org/guide/typescript/overview.html#project-setup).

# splash-inkflow ：泼墨流韵

## meta ：元；thriving ：燊。

## 版本号制定规则（初创不合实际版）

- deploy-prod 分支版本号以 RELEASE 为前缀, develop分支版本号以 CANDIDATE 为前缀,先都为大写形式
- 重大变更定版为 RELEASE-X.0.0 ,其中X为大版本号,每次加一;重大变更定义为:基础数据处理逻辑或基础功能升级或上线/JDK版本升级/漏洞修复
- 功能上线定版为 RELEASE-X.Y.0 ,其中Y为小版本号,每次加一,大版本升级后归零;
- 大量代码重构为 RELEASE-X.Y.0 ,其中Y为小版本号,每次加一,大版本升级后归零;
- bug修复定版为 RELEASE-X.Y.Z ,其中Z为补丁号,每次加一,小版本升级后归零;
- 少量代码重构为 RELEASE-X.Y.Z ,其中Z为补丁号,每次加一,小版本升级后归零;

## 各个模块功能说明

### basic-module

1. 本模块详情如下：
   - 所有外部依赖项由本项目的pom文件引入，版本控制通过 splash-inkflow.pom 文件控制
   - configs 包负责存放基础配置类，主要是各模块使用的默认配置类
   - utils 包负责存放各种基础工具类；*
     *请注意，工具类内部只写非业务逻辑，不允许在工具类中写特定业务的代码;工具类除返回基础类(
     java.lang包中的类)外,一般只能返回异常**
   - resources 路径负责存放本项目的配置文件和内置第三方框架的资源文件

### novel-generator

1.本模块说明如下:

- 小说生成器后台代码
- material.template.deepseek中,prompt 存储 deepseek 可用的提示词模板;request 存储 deepseek 可用的 post 请求模板;response
  存储 deepseek 返回的响应模板
- util 存储所有关于 deepseek 的具体提示词生成、请求拼接、响应解析的逻辑

## 代码简要规约

- 代码提交前一定要进行格式化（ctrl+alt+L）
- 每个方法请尽量不要超过50行，否则会对阅读代码造成困扰
- 方法与变量的命名请使用语义方式命名，使代码如自然语言一样便于被人读懂
- 每个方法的参数数量尽量不要超过六个
- 工具类是不能够被实例化的类，被实例化的类一定是业务场景需要的 model 类
