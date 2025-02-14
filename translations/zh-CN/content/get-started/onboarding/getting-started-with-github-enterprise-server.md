---
title: 开始使用 GitHub Enterprise Server
intro: 'Get started with setting up and managing {% data variables.product.product_location %}.'
versions:
  ghes: '*'
---

This guide will walk you through setting up, configuring and managing {% data variables.product.product_location %} as an enterprise administrator.

{% data variables.product.company_short %} provides two ways to deploy {% data variables.product.prodname_enterprise %}.

- **{% data variables.product.prodname_ghe_cloud %}**
- **{% data variables.product.prodname_ghe_server %}**

{% data variables.product.company_short %} hosts {% data variables.product.prodname_ghe_cloud %}. You can deploy and host {% data variables.product.prodname_ghe_server %} in your own datacenter or a supported cloud provider.

For an overview of how {% data variables.product.product_name %} works, see "[System overview](/admin/overview/system-overview)."

## 第 1 部分：安装 {% data variables.product.product_name %}
To get started with {% data variables.product.product_name %}, you will need to create your enterprise account, install the instance, use the Management Console for initial setup, configure your instance, and manage billing.
### 1. Creating your enterprise account
Before you install {% data variables.product.product_name %}, you can create an enterprise account on {% data variables.product.prodname_dotcom_the_website %} by contacting [{% data variables.product.prodname_dotcom %}'s Sales team](https://enterprise.github.com/contact). An enterprise account on {% data variables.product.prodname_dotcom_the_website %} is useful for billing and for shared features with {% data variables.product.prodname_dotcom_the_website %} via {% data variables.product.prodname_github_connect %}.  更多信息请参阅“[关于企业帐户](/admin/overview/about-enterprise-accounts)”。
### 2. 安装 {% data variables.product.product_name %}
To get started with {% data variables.product.product_name %}, you will need to install the appliance on a virtualization platform of your choice. 更多信息请参阅“[设置 {% data variables.product.prodname_ghe_server %} 实例](/admin/installation/setting-up-a-github-enterprise-server-instance)”。

### 3. Using the Management Console
You will use the Management Console to walk through the initial setup process when first launching {% data variables.product.product_location %}. You can also use the  Management Console to manage instance settings such as the license, domain, authentication, and TLS. For more information, see "[Accessing the management console](/admin/configuration/configuring-your-enterprise/accessing-the-management-console)."

### 4. 配置 {% data variables.product.product_location %}
In addition to the Management Console, you can use the site admin dashboard and the administrative shell (SSH) to manage {% data variables.product.product_location %}. For example, you can configure applications and rate limits, view reports, use command-line utilities. For more information, see "[Configuring your enterprise](/admin/configuration/configuring-your-enterprise)."

You can use the default network settings used by {% data variables.product.product_name %} via the dynamic host configuration protocol (DHCP), or you can also configure the network settings using the virtual machine console. 您还可以配置代理服务器或防火墙规则。 For more information, see "[Configuring network settings](/admin/configuration/configuring-network-settings)."

### 5. 配置高可用性
You can configure {% data variables.product.product_location %} for high availability to minimize the impact of hardware failures and network outages. For more information, see "[Configuring high availability](/admin/enterprise-management/configuring-high-availability)."

### 6. 设置暂存实例
You can set up a staging instance to test modifications, plan for disaster recovery, and try out updates before applying them to {% data variables.product.product_location %}.  更多信息请参阅“[设置暂存实例](/admin/installation/setting-up-a-github-enterprise-server-instance/setting-up-a-staging-instance)”。

### 7. Designating backups and disaster recovery
To protect your production data, you can configure automated backups of {% data variables.product.product_location %} with {% data variables.product.prodname_enterprise_backup_utilities %}. 更多信息请参阅“[在设备上配置备份](/admin/configuration/configuring-your-enterprise/configuring-backups-on-your-appliance)”。

### 8. 管理企业的帐单
Billing for all the organizations and {% data variables.product.product_name %} instances connected to your enterprise account is aggregated into a single bill charge for all of your paid {% data variables.product.prodname_dotcom %}.com services. Enterprise owners and billing managers can access and manage billing settings for enterprise accounts. 更多信息请参阅“[管理帐户的计费](/admin/overview/managing-billing-for-your-enterprise)”。

## Part 2: Organizing and managing your team
As an enterprise owner or administrator, you can manage settings on user, repository, team and organization levels. You can manage members of your enterprise, create and manage organizations, set policies for repository management, and create and manage teams.

### 1. 管理 {% data variables.product.product_location %} 的成员
{% data reusables.getting-started.managing-enterprise-members %}

### 2. 创建组织
{% data reusables.getting-started.creating-organizations %}

### 3. 向组织添加成员
{% data reusables.getting-started.adding-members-to-organizations %}

### 4. 创建团队
{% data reusables.getting-started.creating-teams %}

### 5. 设置组织和存储库权限级别
{% data reusables.getting-started.setting-org-and-repo-permissions %}

### 6. 实施存储库管理策略
{% data reusables.getting-started.enforcing-repo-management-policies %}

## 第 3 部分：安全构建
To increase the security of {% data variables.product.product_location %}, you can configure authentication for enterprise members, use tools and audit logging to stay in compliance, configure security and analysis features for your organizations, and optionally enable {% data variables.product.prodname_GH_advanced_security %}.
### 1. Authenticating enterprise members
You can use {% data variables.product.product_name %}'s built-in authentication method, or you can choose between an established authentication provider, such as CAS, LDAP, or SAML, to integrate your existing accounts and centrally manage user access to {% data variables.product.product_location %}. For more information, see "[Authenticating users for {% data variables.product.product_location %}](/admin/authentication/authenticating-users-for-your-github-enterprise-server-instance)."

You can also require two-factor authentication for each of your organizations. For more information, see "[Requiring two factor authentication for an organization](/admin/user-management/managing-organizations-in-your-enterprise/requiring-two-factor-authentication-for-an-organization)."

### 2. Staying in compliance
You can implement required status checks and commit verifications to enforce your organization's compliance standards and automate compliance workflows. You can also use the audit log for your organization to review actions performed by your team. For more information, see "[Enforcing policy with pre-receive hooks](/admin/policies/enforcing-policy-with-pre-receive-hooks)" and "[Audit logging](/admin/user-management/monitoring-activity-in-your-enterprise/audit-logging)."

{% ifversion ghes %}
### 3. 为组织配置安全功能
{% data reusables.getting-started.configuring-security-features %}
{% endif %}

{% ifversion ghes %}
### 4. Enabling {% data variables.product.prodname_GH_advanced_security %} features
You can upgrade your {% data variables.product.product_name %} license to include {% data variables.product.prodname_GH_advanced_security %}. This provides extra features that help users find and fix security problems in their code, such as code and secret scanning. For more information, see "[{% data variables.product.prodname_GH_advanced_security %} for your enterprise](/admin/advanced-security/enabling-github-advanced-security-for-your-enterprise)."
{% endif %}

## Part 4: Customizing and automating your enterprise's work on {% data variables.product.prodname_dotcom %}
You can customize and automate work in organizations in your enterprise with {% data variables.product.prodname_dotcom %} and {% data variables.product.prodname_oauth_apps %}, {% ifversion fpt or ghec %}{% data variables.product.prodname_dotcom %}{% else %}{% data variables.product.product_name %}{% endif %} API, {% data variables.product.prodname_actions %}, {% data variables.product.prodname_registry %} , and {% data variables.product.prodname_pages %}.

### 1. Building {% data variables.product.prodname_github_apps %} and {% data variables.product.prodname_oauth_apps %}
You can build integrations with the {% ifversion fpt or ghec %}{% data variables.product.prodname_dotcom %}{% else %}{% data variables.product.product_name %}{% endif %} API, such as {% data variables.product.prodname_github_apps %} or {% data variables.product.prodname_oauth_apps %}, for use in organizations in your enterprise to complement and extend your workflows. 更多信息请参阅“[关于应用程序](/developers/apps/getting-started-with-apps/about-apps)”。
### 2. 使用 {% ifversion fpt or ghec %}{% data variables.product.prodname_dotcom %}{% else %}{% data variables.product.product_name %}{% endif %} API
{% data reusables.getting-started.api %}

{% ifversion ghes %}
### 3. 构建 {% data variables.product.prodname_actions %}
{% data reusables.getting-started.actions %}

For more information on enabling and configuring {% data variables.product.prodname_actions %} on {% data variables.product.product_name %}, see "[Getting started with {% data variables.product.prodname_actions %} for {% data variables.product.prodname_ghe_server %}](/admin/github-actions/enabling-github-actions-for-github-enterprise-server/getting-started-with-github-actions-for-github-enterprise-server)."

### 4. 发布和管理 {% data variables.product.prodname_registry %}
{% data reusables.getting-started.packages %}

For more information on enabling and configuring {% data variables.product.prodname_registry %} for {% data variables.product.product_location %}, see "[Getting started with {% data variables.product.prodname_registry %} for your enterprise](/admin/packages/getting-started-with-github-packages-for-your-enterprise)."
{% endif %}

### 5. 使用 {% data variables.product.prodname_pages %}
{% data reusables.getting-started.github-pages-enterprise %}

## Part 5: Connecting with other {% data variables.product.prodname_dotcom %} resources
You can use {% data variables.product.prodname_github_connect %} to share resources.

If you are the owner of both a {% data variables.product.product_name %} instance and a {% data variables.product.prodname_ghe_cloud %} organization or enterprise account, you can enable {% data variables.product.prodname_github_connect %}. {% data variables.product.prodname_github_connect %} allows you to share specific workflows and features between {% data variables.product.product_location %} and {% data variables.product.prodname_ghe_cloud %}, such as unified search and contributions. 更多信息请参阅“[将 {% data variables.product.prodname_ghe_server %} 连接到 {% data variables.product.prodname_ghe_cloud %}](/admin/configuration/managing-connections-between-github-enterprise-server-and-github-enterprise-cloud/connecting-github-enterprise-server-to-github-enterprise-cloud)”。

## Part 6: Using {% data variables.product.prodname_dotcom %}'s learning and support resources
Your enterprise members can learn more about Git and {% data variables.product.prodname_dotcom %} with our learning resources, and you can get the support you need when setting up and managing {% data variables.product.product_location %} with {% data variables.product.prodname_dotcom %} Enterprise Support.

### 1. Reading about {% data variables.product.product_name %} on {% data variables.product.prodname_docs %}

You can read documentation that reflects the features available with {% data variables.product.prodname_ghe_server %}. For more information, see "[About versions of {% data variables.product.prodname_docs %}](/get-started/learning-about-github/about-versions-of-github-docs)."

### 2. Learning with {% data variables.product.prodname_learning %}
{% data reusables.getting-started.learning-lab-enterprise %}

### 3. Working with {% data variables.product.prodname_dotcom %} Enterprise Support
{% data reusables.getting-started.contact-support-enterprise %}
