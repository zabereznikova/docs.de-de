---
title: "Unterschiede zwischen von Internet Explorer und WCF durchgef&#252;hrter Dienstzertifikatsvalidierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Zertifikate [WCF], Dienstzertifikatsvalidierung"
  - "Dienstzertifikatsvalidierung [WCF]"
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Unterschiede zwischen von Internet Explorer und WCF durchgef&#252;hrter Dienstzertifikatsvalidierung
Aufgrund der Unterschiede zwischen der von Internet Explorer und [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] durchgeführten Dienstzertifikatsvalidierung bei der Verwendung von HTTPS ist es möglich, dass Internet Explorer nicht auf die Hilfeseite oder die Web Services Description Language \(WSDL\) eines Diensts zugreifen kann, obwohl ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Client erfolgreich Nachrichten an die Dienstendpunkte senden kann.Dies liegt daran, dass Internet Explorer überprüft, ob das Dienstzertifikat die `ServerAuthentication`\-Objektbezeichner \(OIDs\) in den verbesserten Verwendungsflags aufweist, während [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] eine solche Einschränkung nicht erzwingt.Wenn Internet Explorer die Hilfeseite oder WSDL für den Dienst nicht anzeigen kann, verwenden Sie [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), um auf die Dienstmetadaten zuzugreifen.  
  
## Siehe auch  
 [Unterschiede bei der Zertifikatsvalidierung zwischen HTTPS, SSL über TCP und SOAP\-Sicherheit](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)   
 [Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)