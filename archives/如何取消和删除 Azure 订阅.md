# 如何取消和删除 Azure 订阅

你当前正在访问 Microsoft Azure Global Edition 技术文档网站。 如果需要访问由世纪互联运营的 Microsoft Azure 中国技术文档网站，请访问 [中国技术文档网站](https://docs.azure.cn)。

## 本文内容

如果不再需要 Azure 订阅，可以在 Azure 门户中将其取消。Microsoft 建议你在取消订阅之前执行以下操作，虽然这不是必需的：

- **备份数据**：例如，若要在 Azure 存储或 SQL 中存储数据，请下载一个副本。如果有虚拟机，请在本地保存该虚拟机的映像。
- **关闭服务**：转到“所有资源”页面，**停止**所有正在运行的虚拟机、应用程序或其他服务。
- **考虑迁移数据**：请参阅 [将资源移到新资源组或订阅中](https://learn.microsoft.com/zh-cn/azure/azure-resource-manager/management/move-resource-group-and-subscription)。
- **删除所有资源和所有资源组**：
  - 若要以后以手动方式删除订阅，必须先删除与订阅关联的所有资源。
  - 可能无法删除所有资源，具体取决于配置。例如，有不可变 Blob。有关详细信息，请参阅 [不可变 Blob](https://learn.microsoft.com/zh-cn/azure/storage/blobs/immutable-version-level-worm-policies#scenarios)。
- **更新自定义角色**：如果在 `AssignableScopes` 中有任何引用此订阅的自定义角色，则应更新这些自定义角色以删除此订阅。如果在取消订阅后尝试更新自定义角色，可能会收到报错信息。有关详细信息，请参阅 [排查自定义角色问题](https://learn.microsoft.com/zh-cn/azure/role-based-access-control/troubleshooting#custom-roles) 和 [Azure 自定义角色](https://learn.microsoft.com/zh-cn/azure/role-based-access-control/custom-roles)。

可以移除订阅的所有资源，而不是取消订阅，以防止 [不必要的费用](https://learn.microsoft.com/zh-cn/azure/cost-management-billing/understand/plan-manage-costs#prevent-unwanted-charges)。

**注意**：取消最后一个 Azure 订阅后，可以在满足所有必要条件后将其删除。

## 最终费用和最后一笔账单

取消最后一个订阅后，Azure 将在 72 小时内或三个日历日内结束当前计费周期。计费周期结束后，你将收到最后一个计费周期中产生的使用情况的最终账单（计费）。也就是说，你可能不会在取消最后一个订阅的同一天收到最终账单。而是在取消订阅后最多三天收到最终账单。

以下示例演示计费周期的结束方式：

- **企业协议 (EA) 订阅** – 如果计费月在 3 月 31 日结束，则在该日期后的最多 72 小时内更新估算费用。在此示例中，更新截止时间为 4 月 4 日午夜 (UTC)。
- **即用即付订阅** – 如果计费月在 5 月 15 日结束，则在该日期后的最多 72 小时内更新估算费用。在此示例中，更新截止时间为 5 月 19 日午夜 (UTC)。

支付最终账单后，请记住以下几点：

- Azure 不会立即删除数据。如果决定以后重新激活订阅，数据会暂时保留。Azure 不会对暂时保留的数据收费。
- Azure 不会立即删除订阅。
- Azure 永远不会自动删除 Azure 帐户。若要删除 Azure 帐户，请参阅 [如何删除我的 Azure 帐户](https://learn.microsoft.com/zh-cn/azure/cost-management-billing/manage/cancel-azure-subscription#how-do-i-delete-my-azure-account)。

如果取消 Azure 支持计划，则需为剩余的月份付费。取消支持计划不会导致按比例退款。有关详细信息，请参阅 [Azure 支持计划](https://azure.microsoft.com/support/plans/)。

## 谁可以取消订阅？

- 如果不确定你拥有的订阅类型，请参阅 [检查帐户类型](https://learn.microsoft.com/zh-cn/azure/cost-management-billing/manage/view-all-accounts#check-the-type-of-your-account)。
- 如果你没有取消订阅的权限，请联系组织中有权取消订阅的人员。

下表说明了取消订阅所需的权限。

| 订阅类型 | 谁可以取消 |
| --- | --- |
| 通过 Azure 网站注册 Azure 时创建的订阅。例如，当你注册 [Azure 免费帐户](https://azure.microsoft.com/offers/ms-azr-0044p/)、[采用即用即付费率的帐户](https://azure.microsoft.com/offers/ms-azr-0003p/)，或者以 [Visual Studio 订阅者](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/)的身份进行注册时。 | 订阅所有者 |
| [Microsoft 企业协议](https://azure.microsoft.com/pricing/enterprise-agreement/) 和 [Enterprise 开发/测试](https://azure.microsoft.com/offers/ms-azr-0148p/) | 订阅所有者 |
| [Azure 计划](https://azure.microsoft.com/offers/ms-azr-0017g/) 和 [Azure 开发测试计划](https://azure.microsoft.com/offers/ms-azr-0148g/) | 订阅所有者 |

没有订阅所有者角色的帐户管理员无法取消 Azure 订阅。有关详细信息，请参阅 [Azure 经典订阅管理员](https://learn.microsoft.com/zh-cn/azure/role-based-access-control/classic-administrators)。

## 在 Azure 门户中取消订阅

根据环境，订阅取消体验允许：

- 取消订阅
- 为关联的支持计划关闭自动续订
- 停止所有 Azure 订阅资源

如果有与订阅关联的支持计划，会在取消过程中显示。否则不会显示。

如果有任何与订阅关联的 Azure 资源，则会在取消过程中显示。否则不会显示。

根据环境，可以使用以下步骤取消 Azure 支持计划：

1. 导航到成本管理 + 计费概述页。
2. 从**订阅**页中选择要取消的支持计划，以打开支持计划页。
3. 选择“**取消**”以取消支持计划。

订阅所有者可以在 Azure 门户中导航到**订阅**，然后从步骤 3 开始。

**取消订阅步骤**：

1. 在 Azure 门户中，导航到“成本管理 + 计费”。
2. 在左侧菜单中，选择“**订阅**”或“**Azure 订阅**”，具体取决于可用的选项。如果有支持计划，会显示在列表中。
3. 选择要取消的订阅。
4. 在页面顶部，选择**取消**。
5. 如果有任何与订阅关联的资源，则会在页面上显示。在页面顶部，选择“取消订阅”。
6. 选择取消原因。
7. 如果你有支持计划，但没有其他订阅在使用它，请选择**关闭自动续订**。如果有其他订阅在使用支持计划，请清除该选项。
8. 如果有任何与订阅关联的正在运行的资源，则必须选择“关闭资源”。确保已备份要保留的任何数据。
9. 选择“取消订阅”。

如果有任何尚未开具发票的未结费用，会显示估计费用。如前所述，你将在计费周期结束时收到最终账单。

如果你有尚未应用到发票的任何未结额度，则会显示适用于发票的估计额度。有关数据更新频率详细信息，请参阅 [成本和使用情况数据的更新和保留](https://learn.microsoft.com/zh-cn/azure/cost-management-billing/costs/understand-cost-mgt-data#cost-and-usage-data-updates-and-retention)。

**注意**：如果客户提出请求或发生未付款或欺诈的情况，合作伙伴可以暂停或取消订阅。有关详细信息，请参阅 [暂停或取消订阅](https://learn.microsoft.com/zh-cn/partner-center/create-a-new-subscription#suspend-or-cancel-a-subscription)。

## 取消订阅之后会发生什么情况？

取消后，会立即停止计费。但是，可能需要花费多达 10 分钟，取消才会显示在门户中。如果在计费周期中途取消订阅，我们会在周期结束后于标准发票日期发送最终账单。

取消后，你的服务将被禁用。那意味着虚拟机已解除分配，临时 IP 地址已释放，并且存储是只读的。

创建订阅后，计费会立即停止。可以在取消订阅三天后直接使用 Azure 门户将其删除，在“**删除订阅**”选项可用后即可操作。当你的订阅被取消时，Microsoft 会等待 30 到 90 天，然后才会永久删除你的数据，以防你需要访问数据或恢复数据。我们不会因为保留这些数据而向你收费。有关详细信息，请参阅 [Microsoft 信任中心 - 我们如何管理用户的数据](https://go.microsoft.com/fwLink/p/?LinkID=822930)。

**注意**：在取消 Azure 订阅之前，必须手动取消 SaaS 订阅。Azure 订阅取消过程会自动取消即用即付 SaaS 订阅。

## 删除订阅

“删除订阅”选项至少要在取消订阅后 15 分钟才可用。根据订阅类型，可能无法立即删除订阅。

1. 在 Azure 门户中的 [“订阅”页](https://portal.azure.com/#blade/Microsoft_Azure_Billing/SubscriptionsBlade) 上选择你的订阅。
2. 选择要删除的订阅。
3. 在订阅页面顶部，选择**删除**。
4. 如有必要，请键入订阅的名称，然后选择“**删除**”。
   - 满足所有必需条件后，则可以删除订阅。
   - 如果有未满足的必需删除条件，会显示以下页面：
     - 如果“删除资源”未显示绿色复选标记，则表示必须删除某些资源才能删除该订阅。可以选择“查看资源”来导航到“资源”页，以手动删除资源。资源删除后，可能需要等待 10 分钟资源删除状态才能更新，然后订阅才能删除。
     - 如果“手动删除日期”未显示绿色复选标记，则必须等待所需的期限，然后才能删除订阅。

**注意**：
- 取消订阅 90 天后，将会自动删除订阅。
- 你还可以联系 Microsoft 支持部门来帮助你删除订阅。但是，你必须确保不再需要订阅，因为此过程仅允许七天内重新激活订阅。
- 如果你已删除所有资源，但“删除订阅”页显示你仍有活动的资源，那些可能是处于活动状态的隐藏资源。如果有活动的隐藏资源，就不能删除订阅。若要删除它们，请导航到“订阅”> 选择订阅 >“资源”。在页面顶部，选择“管理视图”，然后选择“显示隐藏的类型”。然后，删除资源。
- 如果禁用了 Azure Active Directory 访问权限订阅，则订阅将在取消 90 天后自动删除。无需手动删除它。

## 重新激活订阅

如果意外取消了采用即用即付费率的订阅，可 [在 Azure 门户重新激活订阅](https://learn.microsoft.com/zh-cn/azure/cost-management-billing/manage/subscription-disabled)。

如果你的订阅不是采用即用即付费率的订阅，可在取消后的 90 天内联系支持人员来重新激活订阅。

## 为什么在 Azure 门户上看不到“取消订阅”选项？

你没有取消订阅所需的权限。有关谁可以取消各种类型的订阅的说明，请参阅 [谁可以取消订阅？](https://learn.microsoft.com/zh-cn/azure/cost-management-billing/manage/cancel-azure-subscription#who-can-cancel-a-subscription)。

## 如何删除 Azure 帐户？

*我需要删除我的帐户，包括所有个人信息。我已经取消了有效的（免费试用版）订阅。我没有任何有效的订阅，并且想要完全删除我的帐户*。

- 如果你是通过组织获取的 Microsoft Entra 帐户，则 Microsoft Entra 管理员可以删除该帐户。在那之后，服务被禁用。那意味着虚拟机已解除分配，临时 IP 地址已释放，并且存储是只读的。总之，取消后，会立即停止计费。
- 如果你不是通过组织获取的 Microsoft Entra 帐户，则可以取消 Azure 订阅后再将其删除，然后从该帐户中删除信用卡。虽然该操作不会删除帐户，但会使其无法使用。如果关联的 Microsoft 帐户当前未用于任何其他目的，则还可以进一步操作并将其删除。

## 如何取消 Visual Studio Professional 帐户？

请参阅 [续订和取消](https://learn.microsoft.com/zh-cn/visualstudio/subscriptions/faq/admin/renewal-cancellation) 一文。如果有任何 Visual Studio Azure 订阅，也需要取消和删除它们。

## 当将所有数据移出 Azure 时，将应用哪些数据传输费用？

现在，当通过 Internet 将数据带出到另一个云提供商或本地数据中心时，Azure 将为离开 Azure 的客户提供免费流出量。使用以下步骤提交免费流出量请求。

### 创建支持请求

1. 若要发出退出 Azure 的意图并允许我们满足你的请求，请创建 [Azure 支持请求](https://portal.azure.com/#view/Microsoft_Azure_Support/HelpAndSupportBlade/%7E/overview)并