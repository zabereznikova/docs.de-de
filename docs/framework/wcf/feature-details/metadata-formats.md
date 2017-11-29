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
# <a name="metadata-formats"></a>Metadatenformate
In der folgenden Tabelle werden die von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] unterstützten Metadatenformate aufgeführt.  
  
## <a name="metadata-specifications-and-usage"></a>Metadatenspezifikation und -verwendung  
  
|Protokoll|Spezifikation und Verwendung|  
|--------------|-----------------------------|  
|WSDL 1.1|[Web Services Description Language (WSDL) 1.1](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet WSDL (Web Services Description Language), um Dienste zu beschreiben.|  
|XML-Schema|[XML Schema Part 2: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) und [XML Schema Part 1: Structures Second Edition](http://go.microsoft.com/fwlink/?LinkId=94862)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet das XML-Schema, um in Nachrichten verwendete Datentypen zu beschreiben.|  
|WS-Richtlinie|[Web Services Policy 1.2 – Framework (WS-Richtlinie)](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [Web Services Policy 1.5 – Framework](http://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die WS-Richtlinienspezifikation&#160;1.2 oder&#160;1.5 zusammen mit domänenspezifischen Assertionen, um Dienstanforderungen und -funktionen zu beschreiben.|  
|WS-Richtlinienanhänge|[Web Services Policy 1.2 – Attachment (WS-PolicyAttachment)](http://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementiert WS-Richtlinienanhänge, um an verschiedene Bereiche von WSDL Richtlinienausdrücke anzufügen.|  
|WS-Metadatenaustausch|[Web Services Metadata Exchange (WS-MetadataExchange) Version 1.1](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementiert WS-MetadataExchange zum Abrufen von XML-Schema, WSDL und der WS-Richtlinie.|  
|WS-Adressierungsbindung für WSDL|[Web Services Addressing 1.0 – WSDL-Bindung](http://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementiert die WS-Adressierungsbindung für WSDL, um Adressierungsinformationen anzufügen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Vom System bereitgestellte Interoperabilitätsbindungen unterstützte Webdienstprotokolle](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [WSDL und Richtlinie](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
