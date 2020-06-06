---
title: <add> von <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: a0f68717f765482f53e675458fae63d1a374d6fb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850329"
---
# <a name="add-of-serviceactivations"></a><span data-ttu-id="0a76d-102">\<add> von \<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="0a76d-102">\<add> of \<serviceActivations></span></span>

<span data-ttu-id="0a76d-103">Ein Konfigurationselement, mit dem Sie Aktivierungs Einstellungen für virtuelle Dienste definieren können, die Ihren Windows Communication Foundation (WCF)-Dienst Typen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0a76d-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="0a76d-104">Auf diese Weise können Sie in WAS/IIS gehostete Dienste ohne eine SVC-Datei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0a76d-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceActivations>**](serviceactivations.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  

## <a name="syntax"></a><span data-ttu-id="0a76d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a76d-105">Syntax</span></span>

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0a76d-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0a76d-106">Attributes and Elements</span></span>

<span data-ttu-id="0a76d-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a76d-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0a76d-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="0a76d-108">Attributes</span></span>

|<span data-ttu-id="0a76d-109">attribute</span><span class="sxs-lookup"><span data-stu-id="0a76d-109">Attribute</span></span>|<span data-ttu-id="0a76d-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0a76d-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="0a76d-111">Fabrik</span><span class="sxs-lookup"><span data-stu-id="0a76d-111">factory</span></span>|<span data-ttu-id="0a76d-112">Eine Zeichenfolge, die den CLR-Typnamen der Factory angibt, die ein Dienstaktivierungselement generiert.</span><span class="sxs-lookup"><span data-stu-id="0a76d-112">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|
|<span data-ttu-id="0a76d-113">Dienst</span><span class="sxs-lookup"><span data-stu-id="0a76d-113">service</span></span>|<span data-ttu-id="0a76d-114">Der ServiceType, der den Dienst implementiert (entweder der vollqualifizierte Typname oder der kurze Typname, falls im Ordner "App_Code" enthalten).</span><span class="sxs-lookup"><span data-stu-id="0a76d-114">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|
|<span data-ttu-id="0a76d-115">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="0a76d-115">relativeAddress</span></span>|<span data-ttu-id="0a76d-116">Die relative Adresse innerhalb der aktuellen IIS-Anwendung, z. B. "Service.svc".</span><span class="sxs-lookup"><span data-stu-id="0a76d-116">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="0a76d-117">In WCF 4,0 muss diese relative Adresse eine der bekannten Dateierweiterungen (. svc,. xamlx,...) enthalten. Für die RelativeURL muss keine physische Datei vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="0a76d-117">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0a76d-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a76d-118">Child Elements</span></span>

<span data-ttu-id="0a76d-119">Keine</span><span class="sxs-lookup"><span data-stu-id="0a76d-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0a76d-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a76d-120">Parent Elements</span></span>

|<span data-ttu-id="0a76d-121">Element</span><span class="sxs-lookup"><span data-stu-id="0a76d-121">Element</span></span>|<span data-ttu-id="0a76d-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a76d-122">Description</span></span>|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="0a76d-123">Ein Konfigurationsabschnitt, der Aktivierungseinstellungen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="0a76d-123">A configuration section that describes activation settings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0a76d-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0a76d-124">Remarks</span></span>

<span data-ttu-id="0a76d-125">Im folgenden Beispiel wird gezeigt, wie Aktivierungseinstellungen innerhalb der Datei web.config konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="0a76d-125">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="0a76d-126">Mit dieser Konfiguration können Sie das GreetingService-Element aktivieren, ohne eine SVC-Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0a76d-126">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="0a76d-127">Beachten Sie, dass es sich bei `<serviceHostingEnvironment>` um eine Konfiguration auf Anwendungsebene handelt.</span><span class="sxs-lookup"><span data-stu-id="0a76d-127">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="0a76d-128">Sie müssen das `web.config`-Element, das die Konfiguration enthält, unter dem Stammelement der virtuellen Anwendung platzieren.</span><span class="sxs-lookup"><span data-stu-id="0a76d-128">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="0a76d-129">Außerdem `serviceHostingEnvironment` ist ein von MachineToApplication vererbbarer Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="0a76d-129">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="0a76d-130">Wenn Sie einen einzelnen Dienst im Stammelement des Computers registrieren, erbt jeder Dienst in der Anwendung diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="0a76d-130">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="0a76d-131">Die konfigurationsbasierte Aktivierung unterstützt sowohl die Aktivierung über http als auch über ein anderes Protokoll.</span><span class="sxs-lookup"><span data-stu-id="0a76d-131">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="0a76d-132">Er erfordert Erweiterungen in der relativeAddress, z. b.. svc,. XOML oder. xamlx.</span><span class="sxs-lookup"><span data-stu-id="0a76d-132">It requires extensions in the relativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="0a76d-133">Sie können den bekannten buildProviders eigene Erweiterungen zuordnen, die Ihnen dann ermöglichen, den Dienst über eine beliebige Erweiterung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0a76d-133">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="0a76d-134">Bei einem Konflikt überschreibt der Abschnitt `<serviceActivations>` die SVC-Registrierungen.</span><span class="sxs-lookup"><span data-stu-id="0a76d-134">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a76d-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a76d-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
