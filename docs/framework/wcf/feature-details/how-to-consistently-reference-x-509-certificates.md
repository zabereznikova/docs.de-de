---
title: "Vorgehensweise: Einheitliche Verweise auf X.509-Zertifikate | Microsoft Docs"
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
  - "Zertifikate [WCF], Verweisen auf X.509-Zertifikate"
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Vorgehensweise: Einheitliche Verweise auf X.509-Zertifikate
Sie haben verschiedene Möglichkeiten, Zertifikate anzugeben: anhand des Hashwerts des Zertifikats, anhand des Ausstellers und der Seriennummer oder anhand der Schlüsselkennung des Antragstellers \(Subject Key Identifier, SKI\).Die Schlüsselkennung des Antragstellers gibt den öffentlichen Schlüssel des Zertifikatantagstellers eindeutig an. Sie wird häufig für digitale XML\-Signaturen verwendet.Der SKI\-Wert ist in der Regel als *X.509\-Zertifikatserweiterung* Bestandteil des X.509\-Zertifikats.[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verfügt über einen standardmäßigen *Verweisstil*, der den Aussteller und die Seriennummer verwendet, wenn die SKI\-Erweiterung im Zertifikat fehlt.Enthält das Zertifikat die SKI\-Erweiterung, verwendet der Standardverweis die Schlüsselkennung des Antragstellers, um auf das Zertifikat zu verweisen.Wenn Sie während der Entwicklung einer Anwendung von Zertifikaten, die die SKI\-Erweiterung nicht verwenden, auf Zertifikate umstellen, die die SKI\-Erweiterung verwenden, ändert sich auch der Verweisstil in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-generierten Nachrichten.  
  
 Wenn unabhängig vom Vorhandensein einer SKI\-Erweiterung ein einheitlicher Verweisstil erforderlich ist, kann der gewünschte Verweisstil wie im folgenden Code dargestellt konfiguriert werden.  
  
## Beispiel  
 Im folgenden Beispiel wird ein benutzerdefiniertes Sicherheitsbindungselement erstellt, das einen einzigen einheitlichen Verweisstil, den Namen des Ausstellers und die Seriennummer verwendet.  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## Kompilieren des Codes  
 Die folgenden Namespaces sind zum Kompilieren des Codes erforderlich:  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Security.Tokens>  
  
## Siehe auch  
 [Verwenden von Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)