---
title: <wsdlImporters>
ms.date: 03/30/2017
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
ms.openlocfilehash: 81fb25f6a77456608fd3cb0d5e73f67c7f7867c3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274572"
---
# <a name="wsdlimporters"></a><span data-ttu-id="97a6f-101">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="97a6f-101">\<wsdlImporters></span></span>
<span data-ttu-id="97a6f-102">Dieses Konfigurationselement gibt alle WSDL-Importer an, die WSDL 1.1-Metadaten (Web Services Description Language) mit WS-Richtlinienanhängen importieren.</span><span class="sxs-lookup"><span data-stu-id="97a6f-102">This configuration element specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="97a6f-103">Jedes untergeordnete Element ist ein <`wsdlImporter`>, der die Art und Weise des Imports von Metadaten und der Konvertierung der Informationen in verschiedene Klassen angibt, die Vertrags- und Endpunktinformationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="97a6f-103">Each child element is a <`wsdlImporter`> that specifies the way to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="97a6f-104">Vertrags- und Endpunktinformationen sowie Eigenschaften, die Importfehler offenlegen und Typinformationen akzeptieren, die für den Import- und Konvertierungsvorgang relevant sind, können selektiv importiert werden.</span><span class="sxs-lookup"><span data-stu-id="97a6f-104">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="97a6f-105">Außerdem wird der Import von Bindungsinformationen und -eigenschaften unterstützt, die Zugriff auf Richtliniendokumente, WSDL-Dokumente, WSDL-Erweiterungen und XML-Schemadokumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="97a6f-105">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97a6f-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97a6f-106">See also</span></span>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="97a6f-107">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="97a6f-107">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="97a6f-108">Clients</span><span class="sxs-lookup"><span data-stu-id="97a6f-108">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
