---
title: Metadatenformate
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: e7208a8d5fd6d100ac2a2c4fb1369a571c63e7fc
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212172"
---
# <a name="metadata-formats"></a>Metadatenformate
Windows Communication Foundation (WCF) unterstützt die Metadatenformate in der folgenden Tabelle.  
  
## <a name="metadata-specifications-and-usage"></a>Metadatenspezifikation und -verwendung  
  
|Protokoll|Spezifikation und Verwendung|  
|--------------|-----------------------------|  
|WSDL 1.1|[Web Services Description Language (WSDL) 1,1](https://www.w3.org/TR/wsdl/)<br /><br /> WCF verwendet Web Services Description Language (WSDL) zum Beschreiben von Diensten.|  
|XML-Schema|[XML Schema Part 2: Datatypes Second Edition](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/) und [XML Schema Part 1: Structures Second Edition](https://www.w3.org/TR/2004/REC-xmlschema-1-20041028/)<br /><br /> WCF verwendet das XML-Schema, um die in Nachrichten verwendeten Datentypen zu beschreiben.|  
|WS-Richtlinie|[Webdienst Richtlinie 1,2-Framework (WS-Policy)](https://www.w3.org/Submission/WS-Policy/)<br /><br /> [Webdienst Richtlinie 1,5-Framework](https://www.w3.org/TR/ws-policy/)<br /><br /> WCF verwendet die WS-Policy 1,2-oder 1,5-Spezifikationen mit domänenspezifischen Assertionen, um Dienst Anforderungen und-Funktionen zu beschreiben.|  
|WS-Richtlinienanhänge|[Webdienst Richtlinie 1,2-Anlage (WS-PolicyAttachment)](https://www.w3.org/Submission/WS-PolicyAttachment/)<br /><br /> WCF implementiert WS-Richtlinien Anhänge, um Richtlinien Ausdrücke in verschiedenen Bereichen in WSDL anzufügen.|  
|WS-Metadatenaustausch|[Web Services Metadata Exchange (WS-MetadataExchange) Version 1,1](https://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF implementiert WS-MetadataExchange zum Abrufen von XML-Schema, WSDL und WS-Policy.|  
|WS-Adressierungsbindung für WSDL|[Webdienst Adressierung 1,0-WSDL-Bindung](https://www.w3.org/TR/ws-addr-wsdl/)<br /><br /> WCF implementiert die WS-Adressierungs Bindung für WSDL, um Adressierungs Informationen in WSDL anzufügen.|  
  
## <a name="see-also"></a>Siehe auch

- [Durch vom System bereitgestellte Interoperabilitätsbindungen unterstützte Webdienstprotokolle](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL und Richtlinie](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
