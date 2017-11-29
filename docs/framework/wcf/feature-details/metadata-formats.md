---
title: Metadatenformate
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d250b57282d24780dcdd1e045f18d7528bd86a90
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="metadata-formats"></a><span data-ttu-id="566ec-102">Metadatenformate</span><span class="sxs-lookup"><span data-stu-id="566ec-102">Metadata Formats</span></span>
<span data-ttu-id="566ec-103">In der folgenden Tabelle werden die von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] unterstützten Metadatenformate aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="566ec-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] supports the metadata formats in the following table.</span></span>  
  
## <a name="metadata-specifications-and-usage"></a><span data-ttu-id="566ec-104">Metadatenspezifikation und -verwendung</span><span class="sxs-lookup"><span data-stu-id="566ec-104">Metadata Specifications and Usage</span></span>  
  
|<span data-ttu-id="566ec-105">Protokoll</span><span class="sxs-lookup"><span data-stu-id="566ec-105">Protocol</span></span>|<span data-ttu-id="566ec-106">Spezifikation und Verwendung</span><span class="sxs-lookup"><span data-stu-id="566ec-106">Specification and usage</span></span>|  
|--------------|-----------------------------|  
|<span data-ttu-id="566ec-107">WSDL 1.1</span><span class="sxs-lookup"><span data-stu-id="566ec-107">WSDL 1.1</span></span>|[<span data-ttu-id="566ec-108">Web Services Description Language (WSDL) 1.1</span><span class="sxs-lookup"><span data-stu-id="566ec-108">Web Services Description Language (WSDL) 1.1</span></span>](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="566ec-109"> verwendet WSDL (Web Services Description Language), um Dienste zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="566ec-109"> uses Web Services Description Language (WSDL) to describe services.</span></span>|  
|<span data-ttu-id="566ec-110">XML-Schema</span><span class="sxs-lookup"><span data-stu-id="566ec-110">XML Schema</span></span>|<span data-ttu-id="566ec-111">[XML Schema Part 2: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) und [XML Schema Part 1: Structures Second Edition](http://go.microsoft.com/fwlink/?LinkId=94862)</span><span class="sxs-lookup"><span data-stu-id="566ec-111">[XML Schema Part 2: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) and [XML Schema Part 1: Structures Second Edition](http://go.microsoft.com/fwlink/?LinkId=94862)</span></span><br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="566ec-112"> verwendet das XML-Schema, um in Nachrichten verwendete Datentypen zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="566ec-112"> uses the XML Schema to describe data types used in messages.</span></span>|  
|<span data-ttu-id="566ec-113">WS-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="566ec-113">WS Policy</span></span>|[<span data-ttu-id="566ec-114">Web Services Policy 1.2 – Framework (WS-Richtlinie)</span><span class="sxs-lookup"><span data-stu-id="566ec-114">Web Services Policy 1.2 - Framework (WS-Policy)</span></span>](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [<span data-ttu-id="566ec-115">Web Services Policy 1.5 – Framework</span><span class="sxs-lookup"><span data-stu-id="566ec-115">Web Services Policy 1.5 - Framework</span></span>](http://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="566ec-116"> verwendet die WS-Richtlinienspezifikation&#160;1.2 oder&#160;1.5 zusammen mit domänenspezifischen Assertionen, um Dienstanforderungen und -funktionen zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="566ec-116"> uses the WS-Policy 1.2 or 1.5 specifications with domain-specific assertions to describe service requirements and capabilities.</span></span>|  
|<span data-ttu-id="566ec-117">WS-Richtlinienanhänge</span><span class="sxs-lookup"><span data-stu-id="566ec-117">WS Policy Attachments</span></span>|[<span data-ttu-id="566ec-118">Web Services Policy 1.2 – Attachment (WS-PolicyAttachment)</span><span class="sxs-lookup"><span data-stu-id="566ec-118">Web Services Policy 1.2 - Attachment (WS-PolicyAttachment)</span></span>](http://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="566ec-119"> implementiert WS-Richtlinienanhänge, um an verschiedene Bereiche von WSDL Richtlinienausdrücke anzufügen.</span><span class="sxs-lookup"><span data-stu-id="566ec-119"> implements WS-Policy Attachments to attach policy expressions at various scopes in WSDL.</span></span>|  
|<span data-ttu-id="566ec-120">WS-Metadatenaustausch</span><span class="sxs-lookup"><span data-stu-id="566ec-120">WS Metadata Exchange</span></span>|[<span data-ttu-id="566ec-121">Web Services Metadata Exchange (WS-MetadataExchange) Version 1.1</span><span class="sxs-lookup"><span data-stu-id="566ec-121">Web Services Metadata Exchange (WS-MetadataExchange) version 1.1</span></span>](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="566ec-122"> implementiert WS-MetadataExchange zum Abrufen von XML-Schema, WSDL und der WS-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="566ec-122"> implements WS-MetadataExchange to retrieve XML Schema, WSDL, and WS-Policy.</span></span>|  
|<span data-ttu-id="566ec-123">WS-Adressierungsbindung für WSDL</span><span class="sxs-lookup"><span data-stu-id="566ec-123">WS Addressing Binding for WSDL</span></span>|[<span data-ttu-id="566ec-124">Web Services Addressing 1.0 – WSDL-Bindung</span><span class="sxs-lookup"><span data-stu-id="566ec-124">Web Services Addressing 1.0 - WSDL Binding</span></span>](http://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="566ec-125"> implementiert die WS-Adressierungsbindung für WSDL, um Adressierungsinformationen anzufügen.</span><span class="sxs-lookup"><span data-stu-id="566ec-125"> implements WS-Addressing Binding for WSDL to attach addressing information in WSDL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="566ec-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="566ec-126">See Also</span></span>  
 [<span data-ttu-id="566ec-127">Vom System bereitgestellte Interoperabilitätsbindungen unterstützte Webdienstprotokolle</span><span class="sxs-lookup"><span data-stu-id="566ec-127">Web Services Protocols Supported by System-Provided Interoperability Bindings</span></span>](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [<span data-ttu-id="566ec-128">WSDL und Richtlinie</span><span class="sxs-lookup"><span data-stu-id="566ec-128">WSDL and Policy</span></span>](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
