---
title: <wsdlImporters>
ms.date: 03/30/2017
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
ms.openlocfilehash: da9ab00c86e7f2657bfc28724d328ccbbc6957b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915168"
---
# <a name="wsdlimporters"></a><span data-ttu-id="bff47-101">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="bff47-101">\<wsdlImporters></span></span>
<span data-ttu-id="bff47-102">Dieses Konfigurationselement gibt alle WSDL-Importer an, die WSDL 1.1-Metadaten (Web Services Description Language) mit WS-Richtlinienanhängen importieren.</span><span class="sxs-lookup"><span data-stu-id="bff47-102">This configuration element specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="bff47-103">Jedes untergeordnete Element ist ein`wsdlImporter`< >, das angibt, wie Metadaten importiert und in verschiedene Klassen konvertiert werden, die Vertrags-und Endpunkt Informationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="bff47-103">Each child element is a <`wsdlImporter`> that specifies the way to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="bff47-104">Vertrags- und Endpunktinformationen sowie Eigenschaften, die Importfehler offenlegen und Typinformationen akzeptieren, die für den Import- und Konvertierungsvorgang relevant sind, können selektiv importiert werden.</span><span class="sxs-lookup"><span data-stu-id="bff47-104">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="bff47-105">Außerdem wird der Import von Bindungsinformationen und -eigenschaften unterstützt, die Zugriff auf Richtliniendokumente, WSDL-Dokumente, WSDL-Erweiterungen und XML-Schemadokumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="bff47-105">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bff47-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bff47-106">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="bff47-107">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="bff47-107">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="bff47-108">Clients</span><span class="sxs-lookup"><span data-stu-id="bff47-108">Clients</span></span>](../../../wcf/feature-details/clients.md)
