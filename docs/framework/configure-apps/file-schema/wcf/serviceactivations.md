---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 64ae0bfd90ae941fc78515c7936c998201c87485
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855134"
---
# <a name="serviceactivations"></a><span data-ttu-id="25a75-101">\<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="25a75-101">\<serviceActivations></span></span>

<span data-ttu-id="25a75-102">Ein Konfigurationselement, mit dem Sie Einstellungen hinzufügen können, die Aktivierungs Einstellungen für virtuelle Dienste definieren, die Ihren Windows Communication Foundation (WCF)-Dienst Typen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="25a75-102">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="25a75-103">Auf diese Weise können Sie in WAS/IIS gehostete Dienste ohne eine SVC-Datei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="25a75-103">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="25a75-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="25a75-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="25a75-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="25a75-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="25a75-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<servicehoststingenvironment->** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="25a75-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="25a75-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceactivations->**</span><span class="sxs-lookup"><span data-stu-id="25a75-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceActivations>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="25a75-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="25a75-108">Syntax</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="25a75-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="25a75-109">Attributes and Elements</span></span>

<span data-ttu-id="25a75-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="25a75-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="25a75-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="25a75-111">Attributes</span></span>

<span data-ttu-id="25a75-112">Keine</span><span class="sxs-lookup"><span data-stu-id="25a75-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="25a75-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="25a75-113">Child Elements</span></span>

|<span data-ttu-id="25a75-114">Element</span><span class="sxs-lookup"><span data-stu-id="25a75-114">Element</span></span>|<span data-ttu-id="25a75-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25a75-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="25a75-116">\<add></span><span class="sxs-lookup"><span data-stu-id="25a75-116">\<add></span></span>](add-of-serviceactivations.md)|<span data-ttu-id="25a75-117">Fügt ein Konfigurationselement hinzu, das die Aktivierung einer Dienstanwendung angibt.</span><span class="sxs-lookup"><span data-stu-id="25a75-117">Adds a configuration element that specifies the activation of a service application.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="25a75-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="25a75-118">Parent Elements</span></span>

|<span data-ttu-id="25a75-119">Element</span><span class="sxs-lookup"><span data-stu-id="25a75-119">Element</span></span>|<span data-ttu-id="25a75-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25a75-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="25a75-121">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="25a75-121">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="25a75-122">Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="25a75-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|

## <a name="remarks"></a><span data-ttu-id="25a75-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25a75-123">Remarks</span></span>

<span data-ttu-id="25a75-124">Im folgenden Beispiel wird gezeigt, wie Aktivierungseinstellungen innerhalb der Datei web.config konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="25a75-124">The following example shows how to configure activation settings within your web.config file.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```

<span data-ttu-id="25a75-125">Mit dieser Konfiguration können Sie das GreetingService-Element aktivieren, ohne eine SVC-Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="25a75-125">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="25a75-126">Beachten Sie, dass es sich bei `<serviceHostingEnvironment>` um eine Konfiguration auf Anwendungsebene handelt.</span><span class="sxs-lookup"><span data-stu-id="25a75-126">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="25a75-127">Sie müssen das `web.config`-Element, das die Konfiguration enthält, unter dem Stammelement der virtuellen Anwendung platzieren.</span><span class="sxs-lookup"><span data-stu-id="25a75-127">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="25a75-128">Außerdem `serviceHostingEnvironment` ist ein von MachineToApplication vererbbarer Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="25a75-128">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="25a75-129">Wenn Sie einen einzelnen Dienst im Stammelement des Computers registrieren, erbt jeder Dienst in der Anwendung diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="25a75-129">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="25a75-130">Die konfigurationsbasierte Aktivierung unterstützt sowohl die Aktivierung über http als auch über ein anderes Protokoll.</span><span class="sxs-lookup"><span data-stu-id="25a75-130">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="25a75-131">Er erfordert Erweiterungen in der relativeAddress, z. b. svc,. XOML oder. xamlx.</span><span class="sxs-lookup"><span data-stu-id="25a75-131">It requires extensions in the relativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="25a75-132">Sie können den bekannten buildProviders eigene Erweiterungen zuordnen, die Ihnen dann ermöglichen, den Dienst über eine beliebige Erweiterung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="25a75-132">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="25a75-133">Bei einem Konflikt überschreibt der Abschnitt `<serviceActivations>` die SVC-Registrierungen.</span><span class="sxs-lookup"><span data-stu-id="25a75-133">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="25a75-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25a75-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
