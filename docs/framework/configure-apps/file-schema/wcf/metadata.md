---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 028e4d3fbe7bce06caa7497c8f95f3b293a4b068
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855227"
---
# <a name="metadata"></a><span data-ttu-id="1c3b3-101">\<Metadaten></span><span class="sxs-lookup"><span data-stu-id="1c3b3-101">\<metadata></span></span>
<span data-ttu-id="1c3b3-102">Gibt an, wie Dienstmetadaten verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="1c3b3-102">Specifies how service metadata can be processed.</span></span>  
  
<span data-ttu-id="1c3b3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1c3b3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1c3b3-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1c3b3-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1c3b3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="1c3b3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="1c3b3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Metadaten>**</span><span class="sxs-lookup"><span data-stu-id="1c3b3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<metadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c3b3-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c3b3-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <client>
    <metadata>
      <policyImporters>
        <policyImporter type="string" />
      </policyImporters>
      <wsdlImporters>
        <wsdlImporter type="string" />
      </wsdlImporters>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c3b3-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1c3b3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1c3b3-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1c3b3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c3b3-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="1c3b3-110">Attributes</span></span>  
 <span data-ttu-id="1c3b3-111">Keine</span><span class="sxs-lookup"><span data-stu-id="1c3b3-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1c3b3-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1c3b3-112">Child Elements</span></span>  
  
|<span data-ttu-id="1c3b3-113">Element</span><span class="sxs-lookup"><span data-stu-id="1c3b3-113">Element</span></span>|<span data-ttu-id="1c3b3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c3b3-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c3b3-115">\<policyimport-></span><span class="sxs-lookup"><span data-stu-id="1c3b3-115">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="1c3b3-116">Gibt alle Richtlinienimporter an, die den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuern.</span><span class="sxs-lookup"><span data-stu-id="1c3b3-116">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="1c3b3-117">Mit einem Richtlinienimporter werden benutzerdefinierte Richtlinienerklärungen über Bindungsfeatures gesucht, und es wird ein benutzerdefiniertes Bindungselement angefügt, mit dem die für die Erklärung erforderlichen Features implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="1c3b3-117">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="1c3b3-118">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="1c3b3-118">\<wsdlImporters></span></span>](wsdlimporters.md)|<span data-ttu-id="1c3b3-119">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="1c3b3-119">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="1c3b3-120">Ein WSDL-Importer wird zum Importieren von Metadaten und zum Konvertieren der Informationen in verschiedene Klassen verwendet, die Vertrags- und Endpunktinformationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="1c3b3-120">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="1c3b3-121">Vertrags- und Endpunktinformationen sowie Eigenschaften, die Importfehler offenlegen und Typinformationen akzeptieren, die für den Import- und Konvertierungsvorgang relevant sind, können selektiv importiert werden.</span><span class="sxs-lookup"><span data-stu-id="1c3b3-121">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="1c3b3-122">Außerdem wird der Import von Bindungsinformationen und -eigenschaften unterstützt, die Zugriff auf Richtliniendokumente, WSDL-Dokumente, WSDL-Erweiterungen und XML-Schemadokumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1c3b3-122">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c3b3-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1c3b3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1c3b3-124">Element</span><span class="sxs-lookup"><span data-stu-id="1c3b3-124">Element</span></span>|<span data-ttu-id="1c3b3-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c3b3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c3b3-126">\<client></span><span class="sxs-lookup"><span data-stu-id="1c3b3-126">\<client></span></span>](client.md)|<span data-ttu-id="1c3b3-127">Der Clientabschnitt definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="1c3b3-127">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c3b3-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c3b3-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="1c3b3-129">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="1c3b3-129">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="1c3b3-130">Clients</span><span class="sxs-lookup"><span data-stu-id="1c3b3-130">Clients</span></span>](../../../wcf/feature-details/clients.md)
