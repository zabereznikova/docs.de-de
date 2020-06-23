---
title: Verwenden von System.Transactions in ASP.NET
description: Verwenden Sie "System. Transactions" in einer ASP.NET-Anwendung. Aktivieren Sie Berechtigungen für verteilte Transaktionen, und arbeiten Sie mit der dynamischen Kompilierung.
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: 48907faf99953e34d045a1e0d79eed8a788187b5
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141643"
---
# <a name="using-systemtransactions-in-aspnet"></a><span data-ttu-id="cce7c-104">Verwenden von System.Transactions in ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cce7c-104">Using System.Transactions in ASP.NET</span></span>
<span data-ttu-id="cce7c-105">In diesem Thema wird beschrieben, wie Sie <xref:System.Transactions> in einer ASP.NET-Anwendung erfolgreich verwenden können.</span><span class="sxs-lookup"><span data-stu-id="cce7c-105">This topic describes how you can successfully use <xref:System.Transactions> inside an ASP.NET application.</span></span>

## <a name="enable-distributedtransactionpermission-in-aspnet"></a><span data-ttu-id="cce7c-106">Aktivieren von DistributedTransactionPermission in ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cce7c-106">Enable DistributedTransactionPermission in ASP.NET</span></span>
 <span data-ttu-id="cce7c-107"><xref:System.Transactions>unterstützt teilweise vertrauenswürdige Aufrufer und wird mit dem- `AllowPartiallyTrustedCallers` Attribut (APTCA) markiert.</span><span class="sxs-lookup"><span data-stu-id="cce7c-107"><xref:System.Transactions> supports partially trusted callers and is marked with the `AllowPartiallyTrustedCallers` attribute (APTCA).</span></span> <span data-ttu-id="cce7c-108">Die Vertrauens Ebenen für <xref:System.Transactions> werden basierend auf den Ressourcentypen (z. b. Systemspeicher, freigegebene prozessübergreifende Ressourcen, systemweite Ressourcen und andere Ressourcen) definiert, die verfügbar macht, <xref:System.Transactions> und der Vertrauens Ebene, die für den Zugriff auf diese Ressourcen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="cce7c-108">The trust levels for <xref:System.Transactions> are defined based on the types of resources (for example, system memory, shared process-wide resources, system-wide resources, and other resources) that <xref:System.Transactions> exposes and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="cce7c-109">In einer teilweise vertrauenswürdigen Umgebung kann eine nicht vollständig vertrauenswürdige Assembly Transaktionen nur innerhalb der Anwendungsdomäne nutzen (in diesem Fall ist die einzige geschützte Ressource der Systemspeicher), sofern ihr nicht die <xref:System.Transactions.DistributedTransactionPermission>erteilt wird.</span><span class="sxs-lookup"><span data-stu-id="cce7c-109">In a partial-trust environment, a non-full trust assembly can only use transactions within the Application Domain (in this case, the only resource being protected is system memory), unless it is granted the <xref:System.Transactions.DistributedTransactionPermission>.</span></span>

 <span data-ttu-id="cce7c-110"><xref:System.Transactions.DistributedTransactionPermission> wird immer dann gefordert, wenn die Transaktionsverwaltung eskaliert wird, um vom Microsoft Distributed Transaction Coordinator (MSDTC) verwaltet zu werden.</span><span class="sxs-lookup"><span data-stu-id="cce7c-110"><xref:System.Transactions.DistributedTransactionPermission> is demanded whenever transaction management is escalated to be managed by the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span> <span data-ttu-id="cce7c-111">Diese Art des Szenarios verwendet prozessübergreifende Ressourcen und insbesondere eine globale Ressource, bei der es sich um den reservierten Speicherplatz im MSDTC-Protokoll handelt.</span><span class="sxs-lookup"><span data-stu-id="cce7c-111">This kind of scenario utilizes process-wide resources and particularly a global resource, which is the reserved space in the MSDTC log.</span></span> <span data-ttu-id="cce7c-112">Ein Beispiel für diese Verwendung ist das Web-Front-End einer Datenbank oder Anwendung, die eine Datenbank nutzt, die zu den von ihr bereitgestellten Diensten gehört.</span><span class="sxs-lookup"><span data-stu-id="cce7c-112">An example of this usage is a Web front-end to a database or an application that uses a database as part of the services it provides.</span></span>

 <span data-ttu-id="cce7c-113">ASP.NET verfügt über einen eigenen Satz Vertrauensebenen und ordnet diesen Vertrauensebenen über Richtliniendateien einen spezifischen Satz Berechtigungen zu.</span><span class="sxs-lookup"><span data-stu-id="cce7c-113">ASP.NET has its own set of trust levels and associates a specific set of permissions with these trust levels through policy files.</span></span> <span data-ttu-id="cce7c-114">Weitere Informationen finden Sie unter [ASP.net Trust Levels and Policy files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="cce7c-114">For more information, see [ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)).</span></span> <span data-ttu-id="cce7c-115">Wenn Sie die Windows SDK erstmalig installieren, wird keine der Standardrichtlinien Dateien der ASP.NET zugeordnet <xref:System.Transactions.DistributedTransactionPermission> .</span><span class="sxs-lookup"><span data-stu-id="cce7c-115">When you initially install the Windows SDK, none of the default ASP.NET policy files are associated with the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="cce7c-116">Wenn Ihre Transaktion in einer ASP.NET-Anwendung eskaliert wird, um vom MSDTC verwaltet zu werden, schlägt die Eskalation mit einer <xref:System.Security.SecurityException> fehl, sobald die <xref:System.Transactions.DistributedTransactionPermission> angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="cce7c-116">As such, when your transaction in an ASP.NET application is escalated to be managed by the MSDTC, the escalation fails with a <xref:System.Security.SecurityException> upon demanding the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="cce7c-117">Um die Transaktionseskalation in einer teilweise vertrauenswürdigen ASP.NET-Umgebung zu ermöglichen, müssen Sie die <xref:System.Transactions.DistributedTransactionPermission> auf denselben Vertrauensebenen erteilen wie <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="cce7c-117">To enable transaction escalation in an ASP.NET partial trust environment, you should grant the <xref:System.Transactions.DistributedTransactionPermission> in the same default trust levels as those of <xref:System.Data.SqlClient.SqlClientPermission>.</span></span> <span data-ttu-id="cce7c-118">Sie können entweder Ihre eigene benutzerdefinierte Vertrauensebene und Richtliniendatei konfigurieren, um die Eskalation zu ermöglichen, oder die Standardrichtliniendateien **Web_hightrust.config** und **Web_mediumtrust.config**ändern.</span><span class="sxs-lookup"><span data-stu-id="cce7c-118">You can either configure your own custom trust level and policy file to support this, or you can modify the default policy files, which are **Web_hightrust.config** and **Web_mediumtrust.config**.</span></span>

 <span data-ttu-id="cce7c-119">Um die Richtlinien Dateien zu ändern, fügen Sie `SecurityClass` `DistributedTransactionPermission` dem-Element `SecurityClasses` unter dem-Element ein-Element hinzu, `PolicyLevel` und fügen Sie ein entsprechendes- `IPermission` Element unter der ASP.net `NamedPermissionSet` für System. Transactions hinzu.</span><span class="sxs-lookup"><span data-stu-id="cce7c-119">To modify the policy files, add a `SecurityClass` element for `DistributedTransactionPermission` to the `SecurityClasses` element under the `PolicyLevel` element and add a corresponding `IPermission` element under the ASP.NET `NamedPermissionSet` for System.Transactions.</span></span> <span data-ttu-id="cce7c-120">Die folgende Konfigurationsdatei veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="cce7c-120">The following configuration file demonstrates this.</span></span>

```xml
<SecurityClasses>
   <SecurityClass Name="DistributedTransactionPermission" Description="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
...
</SecurityClasses>

<PermissionSet
  class="NamedPermissionSet"
  version="1"
  Name="ASP.Net">
     <IPermission
        class="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
        version="1"
        Unrestricted="true"
     />
...
</PermissionSet>
```

 <span data-ttu-id="cce7c-121">Weitere Informationen zur ASP.NET-Sicherheitsrichtlinie finden Sie unter [SecurityPolicy-Element (ASP.net-Einstellungs Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="cce7c-121">For more information about ASP.NET security policy, see [securityPolicy Element (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).</span></span>

## <a name="dynamic-compilation"></a><span data-ttu-id="cce7c-122">Dynamische Kompilierung</span><span class="sxs-lookup"><span data-stu-id="cce7c-122">Dynamic Compilation</span></span>
 <span data-ttu-id="cce7c-123">Wenn Sie <xref:System.Transactions> zur Verwendung in eine ASP.NET-Anwendung importieren möchten, die bei Zugriff dynamisch kompiliert wird, sollten Sie einen Verweis auf die <xref:System.Transactions>-Assembly in die Konfigurationsdatei einfügen.</span><span class="sxs-lookup"><span data-stu-id="cce7c-123">If you want to import and use <xref:System.Transactions> in an ASP.NET application that is dynamically compiled on access, you should place a reference to the <xref:System.Transactions> assembly in the configuration file.</span></span> <span data-ttu-id="cce7c-124">Insbesondere sollte der Verweis im `compilation/assemblies` Abschnitt der standardmäßigen Stamm **Web.config** Konfigurationsdatei oder der Konfigurationsdatei einer spezifischen Webanwendung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cce7c-124">Specifically, the reference should be added under the `compilation/assemblies` section of the default root **Web.config** configuration file, or a specific Web application's configuration file.</span></span> <span data-ttu-id="cce7c-125">Das wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cce7c-125">The following example demonstrates this.</span></span>

```xml
<configuration>
   <system.web>
      <compilation>
         <assemblies>
      <add assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
         </assemblies>
      </compilation>
   </system.web>
</configuration>
```

 <span data-ttu-id="cce7c-126">Weitere Informationen finden Sie unter [Add-Element für Assemblys für die Kompilierung (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="cce7c-126">For more information, see [add Element for assemblies for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).</span></span>

## <a name="see-also"></a><span data-ttu-id="cce7c-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cce7c-127">See also</span></span>

- <span data-ttu-id="cce7c-128">[ASP.net-Vertrauens Ebenen und-Richtlinien Dateien](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cce7c-128">[ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))</span></span>
- <span data-ttu-id="cce7c-129">[securityPolicy-Element (ASP.NET-Einstellungsschema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cce7c-129">[securityPolicy Element (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))</span></span>
- [<span data-ttu-id="cce7c-130">Eskalation der Transaktionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="cce7c-130">Transaction Management Escalation</span></span>](transaction-management-escalation.md)
