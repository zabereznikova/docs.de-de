---
title: Metadatenformate
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: a3c6b1f551d1bff8c68a91f33e62df289d2078cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493437"
---
# <a name="metadata-formats"></a>Metadatenformate
Windows Communication Foundation (WCF) unterstützten Metadatenformate in der folgenden Tabelle aufgeführt.  
  
## <a name="metadata-specifications-and-usage"></a>Metadatenspezifikation und -verwendung  
  
|Protokoll|Spezifikation und Verwendung|  
|--------------|-----------------------------|  
|WSDL 1.1|[Web Services Description Language (WSDL) 1.1](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> WCF verwendet Web Services Description Language (WSDL) zum Beschreiben von Diensten.|  
|XML-Schema|[XML Schema Part 2: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) und [XML Schema Part 1: Structures Second Edition](http://go.microsoft.com/fwlink/?LinkId=94862)<br /><br /> WCF verwendet das XML-Schema, um in Nachrichten verwendete Datentypen zu beschreiben.|  
|WS-Richtlinie|[Web Services Policy 1.2 – Framework (WS-Richtlinie)](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [Web Services Policy 1.5 – Framework](http://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> WCF verwendet die WS-Richtlinienspezifikation 1.2 oder 1.5 zusammen mit domänenspezifischen Assertionen zur Beschreibung von dienstanforderungen und -Funktionen.|  
|WS-Richtlinienanhänge|[Web Services Policy 1.2 – Attachment (WS-PolicyAttachment)](http://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> WCF implementiert die WS-Richtlinienanhängen um an verschiedene Bereiche von WSDL Richtlinienausdrücke anzufügen.|  
|WS-Metadatenaustausch|[Web Services Metadata Exchange (WS-MetadataExchange) Version 1.1](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF implementiert die WS-MetadataExchange zum Abrufen von XML-Schema, WSDL und WS-Richtlinie.|  
|WS-Adressierungsbindung für WSDL|[Web Services Addressing 1.0 – WSDL-Bindung](http://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> WCF implementiert die WS-Adressierungsbindung für WSDL, um Adressierungsinformationen anzufügen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Durch vom System bereitgestellte Interoperabilitätsbindungen unterstützte Webdienstprotokolle](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [WSDL und Richtlinie](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
