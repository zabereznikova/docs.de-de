---
title: <add> von <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: a0f68717f765482f53e675458fae63d1a374d6fb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850329"
---
# <a name="add-of-serviceactivations"></a><span data-ttu-id="a2fbf-102">\<Fügen Sie > \<von serviceactivations ></span><span class="sxs-lookup"><span data-stu-id="a2fbf-102">\<add> of \<serviceActivations></span></span>

<span data-ttu-id="a2fbf-103">Ein Konfigurationselement, mit dem Sie Aktivierungs Einstellungen für virtuelle Dienste definieren können, die Ihren Windows Communication Foundation (WCF)-Dienst Typen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="a2fbf-104">Auf diese Weise können Sie in WAS/IIS gehostete Dienste ohne eine SVC-Datei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="a2fbf-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a2fbf-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a2fbf-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a2fbf-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a2fbf-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<servicehoststingenvironment->** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="a2fbf-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="a2fbf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceactivations->** ](serviceactivations.md)</span><span class="sxs-lookup"><span data-stu-id="a2fbf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceActivations>**](serviceactivations.md)</span></span>\
<span data-ttu-id="a2fbf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="a2fbf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="a2fbf-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2fbf-110">Syntax</span></span>

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a2fbf-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a2fbf-111">Attributes and Elements</span></span>

<span data-ttu-id="a2fbf-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-112">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a2fbf-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="a2fbf-113">Attributes</span></span>

|<span data-ttu-id="a2fbf-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="a2fbf-114">Attribute</span></span>|<span data-ttu-id="a2fbf-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2fbf-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="a2fbf-116">factory</span><span class="sxs-lookup"><span data-stu-id="a2fbf-116">factory</span></span>|<span data-ttu-id="a2fbf-117">Eine Zeichenfolge, die den CLR-Typnamen der Factory angibt, die ein Dienstaktivierungselement generiert.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-117">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|
|<span data-ttu-id="a2fbf-118">Dienst</span><span class="sxs-lookup"><span data-stu-id="a2fbf-118">service</span></span>|<span data-ttu-id="a2fbf-119">Der ServiceType, der den Dienst implementiert (entweder der vollqualifizierte Typname oder der kurze Typname, falls im Ordner "App_Code" enthalten).</span><span class="sxs-lookup"><span data-stu-id="a2fbf-119">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|
|<span data-ttu-id="a2fbf-120">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="a2fbf-120">relativeAddress</span></span>|<span data-ttu-id="a2fbf-121">Die relative Adresse innerhalb der aktuellen IIS-Anwendung, z. B. "Service.svc".</span><span class="sxs-lookup"><span data-stu-id="a2fbf-121">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="a2fbf-122">In WCF 4.0 muss diese relative Adresse eine der gültigen Dateierweiterungen (.svc, .xamlx, …) enthalten. Für relativeUrl muss keine physische Datei vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-122">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a2fbf-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2fbf-123">Child Elements</span></span>

<span data-ttu-id="a2fbf-124">Keine</span><span class="sxs-lookup"><span data-stu-id="a2fbf-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a2fbf-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2fbf-125">Parent Elements</span></span>

|<span data-ttu-id="a2fbf-126">Element</span><span class="sxs-lookup"><span data-stu-id="a2fbf-126">Element</span></span>|<span data-ttu-id="a2fbf-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2fbf-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a2fbf-128">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="a2fbf-128">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="a2fbf-129">Ein Konfigurationsabschnitt, der Aktivierungseinstellungen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-129">A configuration section that describes activation settings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a2fbf-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2fbf-130">Remarks</span></span>

<span data-ttu-id="a2fbf-131">Im folgenden Beispiel wird gezeigt, wie Aktivierungseinstellungen innerhalb der Datei web.config konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-131">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="a2fbf-132">Mit dieser Konfiguration können Sie das GreetingService-Element aktivieren, ohne eine SVC-Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-132">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="a2fbf-133">Beachten Sie, dass es sich bei `<serviceHostingEnvironment>` um eine Konfiguration auf Anwendungsebene handelt.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-133">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="a2fbf-134">Sie müssen das `web.config`-Element, das die Konfiguration enthält, unter dem Stammelement der virtuellen Anwendung platzieren.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-134">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="a2fbf-135">Außerdem `serviceHostingEnvironment` ist ein von MachineToApplication vererbbarer Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-135">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="a2fbf-136">Wenn Sie einen einzelnen Dienst im Stammelement des Computers registrieren, erbt jeder Dienst in der Anwendung diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-136">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="a2fbf-137">Die konfigurationsbasierte Aktivierung unterstützt sowohl die Aktivierung über http als auch über ein anderes Protokoll.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-137">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="a2fbf-138">Er erfordert Erweiterungen in der relativeAddress, z. b. svc,. XOML oder. xamlx.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-138">It requires extensions in the relativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="a2fbf-139">Sie können den bekannten buildProviders eigene Erweiterungen zuordnen, die Ihnen dann ermöglichen, den Dienst über eine beliebige Erweiterung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-139">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="a2fbf-140">Bei einem Konflikt überschreibt der Abschnitt `<serviceActivations>` die SVC-Registrierungen.</span><span class="sxs-lookup"><span data-stu-id="a2fbf-140">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2fbf-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2fbf-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
