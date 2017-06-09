---
title: "Bereitstellen von WCF-Anwendungen mit ClickOnce | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Bereitstellen von WCF-Anwendungen mit ClickOnce
Clientanwendungen mit [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] werden möglicherweise mit ClickOnce\-Technologie bereitgestellt.Diese Technologie ermöglicht es, den von der Codezugriffssicherheit bereitgestellten Laufzeitsicherheitsschutz zu nutzen, sofern die Clientanwendungen digital mit einem vertrauenswürdigen Zertifikat signiert sind.Das Zertifikat, mit dem die ClickOnce\-Anwendung signiert wird, muss sich im Speicher für vertrauenswürdige Herausgeber befinden. Die lokale Sicherheitsrichtlinie auf dem Clientcomputer muss so konfiguriert sein, dass signierte Anwendungen mit dem Zertifikat des Herausgebers Berechtigungen für volle Vertrauenswürdigkeit erhalten.  
  
 Weitere Informationen über das Konfigurieren von ClickOnce\-Anwendungen und vertrauenswürdigen Herausgebern finden Sie unter [Konfigurieren von vertrauenswürdigen ClickOnce\-Herausgebern](http://go.microsoft.com/fwlink/?LinkId=94774) \(möglicherweise in englischer Sprache\).  
  
## Siehe auch  
 [Überblick über die Bereitstellung vertrauenswürdiger Anwendungen](http://go.microsoft.com/fwlink/?LinkId=94775)   
 [ClickOnce\-Bereitstellung für Windows Forms\-Anwendungen](http://go.microsoft.com/fwlink/?LinkId=94776)