---
title: <wsdlImporters>
ms.date: 03/30/2017
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
ms.openlocfilehash: c88fb549674f9cad59c4e23a0cc4099a378bec9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158577"
---
# \<wsdlImporters>

<span data-ttu-id="750fb-101">Dieses Konfigurationselement gibt alle WSDL-Importer an, die WSDL 1.1-Metadaten (Web Services Description Language) mit WS-Richtlinienanhängen importieren.</span><span class="sxs-lookup"><span data-stu-id="750fb-101">This configuration element specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="750fb-102">Jedes untergeordnete Element ist ein <`wsdlImporter`>, das angibt, wie Metadaten importiert und in verschiedene Klassen konvertiert werden, die Vertrags-und Endpunkt Informationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="750fb-102">Each child element is a <`wsdlImporter`> that specifies the way to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="750fb-103">Vertrags- und Endpunktinformationen sowie Eigenschaften, die Importfehler offenlegen und Typinformationen akzeptieren, die für den Import- und Konvertierungsvorgang relevant sind, können selektiv importiert werden.</span><span class="sxs-lookup"><span data-stu-id="750fb-103">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="750fb-104">Außerdem wird der Import von Bindungsinformationen und -eigenschaften unterstützt, die Zugriff auf Richtliniendokumente, WSDL-Dokumente, WSDL-Erweiterungen und XML-Schemadokumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="750fb-104">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="750fb-105">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="750fb-105">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="750fb-106">WCF-Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="750fb-106">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="750fb-107">Clients</span><span class="sxs-lookup"><span data-stu-id="750fb-107">Clients</span></span>](../../../wcf/feature-details/clients.md)
