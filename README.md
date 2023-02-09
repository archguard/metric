# metric

> The metric model of all ArchGuard

## ArchGuard 1.x

### Quality: Code

| 坏味道        | 英文名                                        | 解释                                        | 影响                | 来源   | 备注  |
|------------|--------------------------------------------|-------------------------------------------|-------------------|------|-----|
| 可变数据       | Mutable Data                               | 一个变量可以被多处修改                               | Bug 的源泉           | 《重构》 |     |
| 发散式变化      | Divergent Change                           | 某个代码块、方法、类、模块因为不同的原因在不同的方向上发生变化，或者说有多个关注点 | 违背了单一职责原则，维护成本高   | 《重构》 |     |
| 霰弹式修改      | Shotgun Surgery                            | 每次遇到变更，都需要在不同的类作出许多小的修改                   | 概念没有被识别，失去内聚性     | 《重构》 |     |
| 重复的 Switch | Repeated Switches                          | 在不同的地方重复使用相同的条件逻辑                         | 更高的变更成本           | 《重构》 |     |
| 过大的类       | Large Class                                | 一个类承担了太多的职责，不同的访问者使用的是这个类的部分职责            | 违背了接口隔离原则         | 《重构》 |     |
| 异曲同工的类     | Alternative Class With Diffrent Interfaces | 两个类在功能上一致，却声明了不同接口，从而给替换造成困难              |                   | 《重构》 |     |
| 神秘命名       | Mysterious Name                            | 变量、函数、类、模块的命名不能清晰的表明自己的功能和用法；             | 代码可理解性差           | 《重构》 |     |
| 重复代码       | Duplicated Code                            | 在一个以上的位置出现相同的代码结构                         | 更高的变更成本           | 《重构》 |     |
| 过长函数       | Long Function                              | 函数应该尽量短，否则就符合这个坏味道                        | 代码可理解性差；丢失概念      | 《重构》 |     |
| 过长参数列表     | Long Parameter List                        | 参数个数应该尽量少，参数越多，味道越重                       | 代码可理解性差           | 《重构》 |     |
| 注释         | Comments                                   | 如果注释的意思可以通过提炼函数或者改变函数声明说的清楚，这个注释就是多余的     | 容易造成不一致性          | 《重构》 |     |
| 依恋情结       | Feature Envy                               | 数据和访问数据的行为没有放在一起，造成函数间需要更多的交互             | 概念没有被识别，失去内聚性     | 《重构》 |     |
| 数据泥团       | Data Clumps                                | 多个数据经常紧密的一起出现， 却没有被提取成一个概念（类）             | 概念没有被识别，失去内聚性     | 《重构》 |     |
| 基本类型偏执     | Primitive Obsession                        | 偏好使用基本类型，即使表达钱、坐标、范围等概念的时候                | 概念没有被识别，失去内聚性     | 《重构》 |     |
| 冗余的元素      | Lazy Element                               | 没有必要存在的抽象层级，像是只有一个方法的类，只调用了一个函数的函数        | 增加理解的难度，增加冗余代码    | 《重构》 |     |
| 临时字段       | Temporary Field                            | 某个字段只有在某种情况下才用到                           | 概念没有被识别，代码放在错误的位置 | 《重构》 |     |
| 过长的消息链     | Message Chains                             | 客户端代码通过导航路径来访问其他对象，与对象的导航结构紧密耦合           | 过度耦合              | 《重构》 |     |
| 中间人        | Middle Man                                 | 某个类的接口有很多函数都委托给其他类                        | 职责定位不清            | 《重构》 |     |
| 内幕交易       | Insider Trading                            | 两个模块(类）存在大量不明显的耦合                         | 过度耦合              | 《重构》 |     |
| 纯数据类       | Data Class                                 | 一个类只有数据和数据的没有业务逻辑的读写方法                    | 贫血模型，失去内聚性        | 《重构》 |     |
| 被拒绝的遗赠     | Refused Bequest                            | 子类只想继承超类的部分接口或子类复用了超类的实现，但是不愿意支持超类的接口     | 不正确的超类定义；或者不该使用继承 | 《重构》 |     |
| 夸夸其谈通用性    | Speculative Generality                     | 从没有被使用的变量、函数、类等                           | 过度设计，不必要的成本投入     | 《重构》 |     |
| 循环语句       | Loops                                      | 在使用循环的时候，没有考虑是否可以被 Stream API 等方式代替       | 不够简洁，目的不够明确       | 《重构》 |     |

### Quality: Test

已实现

| Name | Description | Reason | 来源  |备注  |
|-----|------|-------------|--------|-----|
| 包含休眠的测试 | Sleepy Test | 测试中包含休眠，如 Thread.sleep() | 测试不稳定，不可重复 | 《重构》 |     |
| 被忽略的测试 | Ignored Test | 测试被忽略，如 @Ignore | 测试不稳定，不可重复 | 《重构》 |     |
| 缺乏校验的测试 | Unverified Test | 测试中没有校验，如 assert | 测试不稳定，不可重复 | 《重构》 |     |
| 包含繁杂判断的测试 | Complex Test | 测试中包含繁杂判断，如 if-else | 测试不稳定，不可重复 | 《重构》 |     |
| 包含冗余打印的测试 | Redundant Print | 测试中包含冗余打印，如 System.out.println() | 测试不稳定，不可重复 | 《重构》 |     |
| 静态方法测试 | Static Method Test | 测试中包含静态方法 | 测试不稳定，不可重复 | 《重构》 |     |

其它（未实现）:

| Name | Description | Reason |  备注  |
|-----|------|-------------|--------|
| 依赖外部资源的测试 | External Resource Test | 测试中依赖外部资源，如数据库 | 测试不稳定，不可重复 | 《重构》 |     |


### Architecture Smell (Not Implemented Yet)

来源: 《[Software Architecture Premises](https://herbertograca.com/2017/07/05/software-architecture-premises/)》  翻译: 《[软件架构预述](https://www.jianshu.com/p/df295f92fb52)》

- 僵化(Rigidity)：如果软件难以修改是因为修改会导致更多关联修改，软件就是僵化的。它就会变成兔子洞：当我们以为修改快要完成时，突然发现还有更多的代码需要修改，把我们拉进无止尽的轮回之中。
- 脆弱(Fragility)：脆弱的软件在修改时，总会出现意料之外的、毫无关联的、无法预测的错误。
- 牢固(Immobility)：如果设计包含一些可以在其它系统中使用的部分，但将这些部分从原系统中分离出来需要大量工作甚至带来许多风险，我们就说设计是牢固的。
- 粘滞(Viscosity)：在一个粘滞的系统中，要做对困难重重，要做错却轻而易举。这意味着通过正常开发实现变更不如用非常手段来得容易。如果执行单元测试和/或编译需要耗费很长时间，开发很可能导跳过这些过程，不跑任何自动化测试就实现非常规的修改，这就是系统范围的粘滞。
- 不必要的重复(Needless repetition)：当时间不够或经验不足导致必要的抽象缺失时，就会产生不必要的重复。这些代码也许并不是直接复制粘贴造成的重复，而是由在不同地方重复定义的相同业务规则带来的。
- 晦涩(Opacity)：代码写得混乱，难以理解，我们需要深人方法实现的细节才能搞清楚代码要干什么。
- 不必要的复杂(Needless complexity)：开发者采用了多种不同的抽象和未来潜在变化的应对措施，来积极地避免其他六种坏味道。良好的软件设计是轻量灵活的，理解起来更容易，最重要的是修改更容易，因此不必预判所有未来的潜在变化。


## ArchGuard 2.x

First Demo:

| Evolution     | Progress          | Governance | Experience       | DevOps               | Quality       | Productivity |
|---------------|-------------------|------------|------------------|----------------------|---------------|--------------|
| Coupling      | Tech Debt         | Document   | Developer        | ChangeFailure Rate   | Test Coverage | Tracing      |
| Hierarchy     | Path toProduction | Gate       | User(limitation) | Deployment Frequency | Code Smell    | Performance  |
| Changeability |                   | Linting    |                  | Lead Time For Change |               | Cost         |
| Modifiability |                   | Metric     |                  | Mean Time To Restore |               |              |


## ArchGuard 3.x

