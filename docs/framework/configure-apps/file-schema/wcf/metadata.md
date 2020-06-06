---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 028e4d3fbe7bce06caa7497c8f95f3b293a4b068
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855227"
---
# \<metadata>
<span data-ttu-id="86687-101">Gibt an, wie Dienstmetadaten verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="86687-101">Specifies how service metadata can be processed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<metadata>**  
  
## <a name="syntax"></a><span data-ttu-id="86687-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="86687-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86687-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="86687-103">Attributes and Elements</span></span>  
 <span data-ttu-id="86687-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="86687-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86687-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="86687-105">Attributes</span></span>  
 <span data-ttu-id="86687-106">Keine</span><span class="sxs-lookup"><span data-stu-id="86687-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="86687-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86687-107">Child Elements</span></span>  
  
|<span data-ttu-id="86687-108">Element</span><span class="sxs-lookup"><span data-stu-id="86687-108">Element</span></span>|<span data-ttu-id="86687-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="86687-109">Description</span></span>|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|<span data-ttu-id="86687-110">Gibt alle Richtlinienimporter an, die den Import von benutzerdefinierten Richtlinienerklärungen über Bindungen steuern.</span><span class="sxs-lookup"><span data-stu-id="86687-110">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="86687-111">Mit einem Richtlinienimporter werden benutzerdefinierte Richtlinienerklärungen über Bindungsfeatures gesucht, und es wird ein benutzerdefiniertes Bindungselement angefügt, mit dem die für die Erklärung erforderlichen Features implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="86687-111">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[\<wsdlImporters>](wsdlimporters.md)|<span data-ttu-id="86687-112">Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="86687-112">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="86687-113">Ein WSDL-Importer wird zum Importieren von Metadaten und zum Konvertieren der Informationen in verschiedene Klassen verwendet, die Vertrags- und Endpunktinformationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="86687-113">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="86687-114">Vertrags- und Endpunktinformationen sowie Eigenschaften, die Importfehler offenlegen und Typinformationen akzeptieren, die für den Import- und Konvertierungsvorgang relevant sind, können selektiv importiert werden.</span><span class="sxs-lookup"><span data-stu-id="86687-114">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="86687-115">Außerdem wird der Import von Bindungsinformationen und -eigenschaften unterstützt, die Zugriff auf Richtliniendokumente, WSDL-Dokumente, WSDL-Erweiterungen und XML-Schemadokumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="86687-115">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="86687-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86687-116">Parent Elements</span></span>  
  
|<span data-ttu-id="86687-117">Element</span><span class="sxs-lookup"><span data-stu-id="86687-117">Element</span></span>|<span data-ttu-id="86687-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="86687-118">Description</span></span>|  
|-------------|-----------------|  
|[\<client>](client.md)|<span data-ttu-id="86687-119">Der Clientabschnitt definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="86687-119">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86687-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86687-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="86687-121">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="86687-121">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="86687-122">Clients</span><span class="sxs-lookup"><span data-stu-id="86687-122">Clients</span></span>](../../../wcf/feature-details/clients.md)
