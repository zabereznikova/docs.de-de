---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: c0c9848d073c799e1f97dd79b375848dfab71e99
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191483"
---
# <a name="metadata"></a><span data-ttu-id="2e856-101">\<metadata></span><span class="sxs-lookup"><span data-stu-id="2e856-101">\<metadata></span></span>
<span data-ttu-id="2e856-102">Gibt an, wie Dienstmetadaten verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="2e856-102">Specifies how service metadata can be processed.</span></span>  
  
 <span data-ttu-id="2e856-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2e856-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2e856-104">\<client></span><span class="sxs-lookup"><span data-stu-id="2e856-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e856-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e856-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e856-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2e856-106">Attributes and Elements</span></span>  
 <span data-ttu-id="2e856-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2e856-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e856-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="2e856-108">Attributes</span></span>  
 <span data-ttu-id="2e856-109">Keine</span><span class="sxs-lookup"><span data-stu-id="2e856-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2e856-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e856-110">Child Elements</span></span>  
  
|<span data-ttu-id="2e856-111">Element</span><span class="sxs-lookup"><span data-stu-id="2e856-111">Element</span></span>|<span data-ttu-id="2e856-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e856-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e856-113">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="2e856-113">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="2e856-114">Gibt alle Richtlinienimporter an, die den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuern.</span><span class="sxs-lookup"><span data-stu-id="2e856-114">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="2e856-115">Mit einem Richtlinienimporter werden benutzerdefinierte Richtlinienerklärungen über Bindungsfeatures gesucht, und es wird ein benutzerdefiniertes Bindungselement angefügt, mit dem die für die Erklärung erforderlichen Features implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e856-115">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="2e856-116">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="2e856-116">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="2e856-117">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e856-117">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="2e856-118">Ein WSDL-Importer wird zum Importieren von Metadaten und zum Konvertieren der Informationen in verschiedene Klassen verwendet, die Vertrags- und Endpunktinformationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="2e856-118">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="2e856-119">Vertrags- und Endpunktinformationen sowie Eigenschaften, die Importfehler offenlegen und Typinformationen akzeptieren, die für den Import- und Konvertierungsvorgang relevant sind, können selektiv importiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e856-119">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="2e856-120">Außerdem wird der Import von Bindungsinformationen und -eigenschaften unterstützt, die Zugriff auf Richtliniendokumente, WSDL-Dokumente, WSDL-Erweiterungen und XML-Schemadokumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2e856-120">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2e856-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e856-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2e856-122">Element</span><span class="sxs-lookup"><span data-stu-id="2e856-122">Element</span></span>|<span data-ttu-id="2e856-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e856-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e856-124">\<client></span><span class="sxs-lookup"><span data-stu-id="2e856-124">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="2e856-125">Der Clientabschnitt definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="2e856-125">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e856-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e856-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="2e856-127">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="2e856-127">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="2e856-128">Clients</span><span class="sxs-lookup"><span data-stu-id="2e856-128">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
