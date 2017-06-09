---
title: "Vorgehensweise: Abrufen eines Zertifikats (WCF) | Microsoft Docs"
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
  - "Zertifikate [WCF], Abrufen"
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Vorgehensweise: Abrufen eines Zertifikats (WCF)
Rufen Sie zuerst Zertifikate ab, um die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Funktionen mit X.509\-Zertifikaten zu verwenden.  
  
### So rufen Sie ein X.509\-Zertifikat ab  
  
1.  Wählen Sie eine der folgenden Optionen aus:  
  
    -   Erwerben Sie ein Zertifikat von einer Zertifizierungsstelle, z. B. VeriSign, Inc.  
  
    -   Richten Sie einen eigenen Zertifikatdienst ein, und lassen Sie die Zertifikate von einer Zertifizierungsstelle signieren.  [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], Windows&\#160;2000 Server, Windows&\#160;2000 Server Datacenter und Windows&\#160;2000 Datacenter Server verfügen alle über Zertifikatdienste mit Public Key Infrastructure \(PKI\)\-Unterstützung.  Verwenden Sie in Windows Server 2008 die Rolle [Active Directory\-Zertifikatsdienste](http://go.microsoft.com/fwlink/?LinkID=153483), um eine Zertifizierungsstelle zu verwalten.  
  
    -   Richten Sie einen eigenen Zertifikatsdienst ein, und lassen Sie die Zertifikate nicht signieren.  
  
    > [!NOTE]
    >  Unabhängig vom gewählten Ansatz muss der Empfänger der SOAP\-Anforderung, die das X.509\-Zertifikat enthält, dem X.509\-Zertifikat vertrauen.  Dies bedeutet, dass sich das X.509\-Zertifikat oder ein Aussteller in der Zertifikatkette im Speicher für vertrauenswürdige Personen befindet und sich das X.509\-Zertifikat nicht im Speicher für nicht vertrauenswürdige Zertifikate befindet.  
  
## Siehe auch  
 [Verwenden von Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Gewusst wie: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)