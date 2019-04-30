---
title: Metadatenformate
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: 55f68f4b56e50b19da19ecc941e9ec537b846006
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038570"
---
# <a name="metadata-formats"></a>Metadatenformate
Windows Communication Foundation (WCF) unterstützt die Metadaten-Formate in der folgenden Tabelle.  
  
## <a name="metadata-specifications-and-usage"></a>Metadatenspezifikation und -verwendung  
  
|Protokoll|Spezifikation und Verwendung|  
|--------------|-----------------------------|  
|WSDL 1.1|[Web Services Description Language (WSDL) 1.1](https://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> WCF verwendet Web Services Description Language (WSDL) zum Beschreiben von Diensten.|  
|XML-Schema|[XML-Schemateil 2: Datatypes Second Edition](https://go.microsoft.com/fwlink/?LinkId=94861) und [XML Schema Part 1: Zweite Auflage von Strukturen](https://go.microsoft.com/fwlink/?LinkId=94862)<br /><br /> WCF verwendet das XML-Schema, um in Nachrichten verwendete Datentypen zu beschreiben.|  
|WS-Richtlinie|[Web Services Policy 1.2 – Framework (WS-Richtlinie)](https://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [Web Services Policy 1.5 – Framework](https://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> WCF verwendet die WS-Richtlinie 1.2 oder 1.5 zusammen mit domänenspezifischen Assertionen, um dienstanforderungen und-Funktionen zu beschreiben.|  
|WS-Richtlinienanhänge|[Web Services Policy 1.2 – Attachment (WS-PolicyAttachment)](https://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> WCF implementiert die WS-Richtlinienanhängen um Richtlinienausdrücke bei verschiedenen Bereiche von WSDL anzufügen.|  
|WS-Metadatenaustausch|[Web Services Metadata Exchange (WS-MetadataExchange) Version 1.1](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF implementiert die WS-MetadataExchange zum Abrufen von XML-Schema, WSDL und WS-Richtlinie.|  
|WS-Adressierungsbindung für WSDL|[Web Services Addressing 1.0 – WSDL-Bindung](https://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> WCF implementiert die WS-Adressierungsbindung für WSDL, um Adressierungsinformationen anzufügen.|  
  
## <a name="see-also"></a>Siehe auch

- [Durch vom System bereitgestellte Interoperabilitätsbindungen unterstützte Webdienstprotokolle](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL und Richtlinie](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
