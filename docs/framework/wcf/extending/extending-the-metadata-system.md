---
title: Erweitern des Metadatensystems
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aca7a7aba7ef4a40100e9858561d197916b71544
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="extending-the-metadata-system"></a><span data-ttu-id="a096f-102">Erweitern des Metadatensystems</span><span class="sxs-lookup"><span data-stu-id="a096f-102">Extending the Metadata System</span></span>
<span data-ttu-id="a096f-103">Beim Metadatensystem von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] handelt es sich um eine Gruppe von Klassen und Schnittstellen, die Metadaten darstellen, die zum Implementieren von dienstbasierten Anwendungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a096f-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="a096f-104">Ändern bzw. erweitern Sie die Klassen, oder implementieren und konfigurieren Sie die Schnittstellen, um benutzerdefinierte Metadaten wie WDSL-Erweiterungen (Web Services Description Language) oder benutzerdefinierte WS-PolicyAttachments-Assertionen zu exportieren oder zu importieren.</span><span class="sxs-lookup"><span data-stu-id="a096f-104">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a096f-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a096f-105">In This Section</span></span>  
 [<span data-ttu-id="a096f-106">Exportieren von benutzerdefinierten Metadaten für eine WCF-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="a096f-106">Exporting Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="a096f-107">Beschreibt die Implementierung und Verwendung der <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType>-Schnittstelle zur Einbettung benutzerdefinierter Richtlinienassertionen in WSDL-Dokumente.</span><span class="sxs-lookup"><span data-stu-id="a096f-107">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="a096f-108">Importieren von benutzerdefinierten Metadaten für eine WCF-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="a096f-108">Importing Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="a096f-109">Beschreibt die Implementierung und Verwendung der <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType>-Schnittstelle zum Lesen und Beantworten benutzerdefinierter Richtlinienassertionen in WSDL-Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="a096f-109">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="a096f-110">Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="a096f-110">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="a096f-111">Beschreibt, wie Metadaten über benutzerdefinierte Bindungen ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="a096f-111">Describes how to exchange metadata over custom bindings.</span></span>
