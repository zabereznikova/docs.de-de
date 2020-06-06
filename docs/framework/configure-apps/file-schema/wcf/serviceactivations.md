---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 64ae0bfd90ae941fc78515c7936c998201c87485
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855134"
---
# \<serviceActivations>

<span data-ttu-id="f20be-101">Ein Konfigurationselement, mit dem Sie Einstellungen hinzufügen können, die Aktivierungs Einstellungen für virtuelle Dienste definieren, die Ihren Windows Communication Foundation (WCF)-Dienst Typen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f20be-101">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="f20be-102">Auf diese Weise können Sie in WAS/IIS gehostete Dienste ohne eine SVC-Datei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f20be-102">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceActivations>**  

## <a name="syntax"></a><span data-ttu-id="f20be-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="f20be-103">Syntax</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f20be-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f20be-104">Attributes and Elements</span></span>

<span data-ttu-id="f20be-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f20be-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f20be-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="f20be-106">Attributes</span></span>

<span data-ttu-id="f20be-107">Keine</span><span class="sxs-lookup"><span data-stu-id="f20be-107">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f20be-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f20be-108">Child Elements</span></span>

|<span data-ttu-id="f20be-109">Element</span><span class="sxs-lookup"><span data-stu-id="f20be-109">Element</span></span>|<span data-ttu-id="f20be-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f20be-110">Description</span></span>|
|-------------|-----------------|
|[\<add>](add-of-serviceactivations.md)|<span data-ttu-id="f20be-111">Fügt ein Konfigurationselement hinzu, das die Aktivierung einer Dienstanwendung angibt.</span><span class="sxs-lookup"><span data-stu-id="f20be-111">Adds a configuration element that specifies the activation of a service application.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f20be-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f20be-112">Parent Elements</span></span>

|<span data-ttu-id="f20be-113">Element</span><span class="sxs-lookup"><span data-stu-id="f20be-113">Element</span></span>|<span data-ttu-id="f20be-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f20be-114">Description</span></span>|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="f20be-115">Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="f20be-115">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f20be-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f20be-116">Remarks</span></span>

<span data-ttu-id="f20be-117">Im folgenden Beispiel wird gezeigt, wie Aktivierungseinstellungen innerhalb der Datei web.config konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f20be-117">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="f20be-118">Mit dieser Konfiguration können Sie das GreetingService-Element aktivieren, ohne eine SVC-Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f20be-118">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="f20be-119">Beachten Sie, dass es sich bei `<serviceHostingEnvironment>` um eine Konfiguration auf Anwendungsebene handelt.</span><span class="sxs-lookup"><span data-stu-id="f20be-119">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="f20be-120">Sie müssen das `web.config`-Element, das die Konfiguration enthält, unter dem Stammelement der virtuellen Anwendung platzieren.</span><span class="sxs-lookup"><span data-stu-id="f20be-120">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="f20be-121">Außerdem `serviceHostingEnvironment` ist ein von MachineToApplication vererbbarer Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="f20be-121">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="f20be-122">Wenn Sie einen einzelnen Dienst im Stammelement des Computers registrieren, erbt jeder Dienst in der Anwendung diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="f20be-122">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="f20be-123">Die konfigurationsbasierte Aktivierung unterstützt sowohl die Aktivierung über http als auch über ein anderes Protokoll.</span><span class="sxs-lookup"><span data-stu-id="f20be-123">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="f20be-124">Er erfordert Erweiterungen in der relativeAddress, z. b.. svc,. XOML oder. xamlx.</span><span class="sxs-lookup"><span data-stu-id="f20be-124">It requires extensions in the relativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="f20be-125">Sie können den bekannten buildProviders eigene Erweiterungen zuordnen, die Ihnen dann ermöglichen, den Dienst über eine beliebige Erweiterung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f20be-125">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="f20be-126">Bei einem Konflikt überschreibt der Abschnitt `<serviceActivations>` die SVC-Registrierungen.</span><span class="sxs-lookup"><span data-stu-id="f20be-126">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="f20be-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f20be-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
