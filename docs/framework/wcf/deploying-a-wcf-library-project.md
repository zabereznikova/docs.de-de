---
title: "Bereitstellen eines WCF-Bibliotheksprojekts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Bereitstellen eines WCF-Bibliotheksprojekts
In diesem Thema wird beschrieben, wie Sie ein [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Dienstbibliotheksprojekt bereitstellen.  
  
## Bereitstellen einer WCF\-Dienstbibliothek  
 Eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstbibliothek ist eine Dynamic Link Library \(DLL\).Als solche kann sie nicht eigenständig ausgeführt werden.Sie muss vielmehr in einer Hostumgebung bereitgestellt werden.Weitere Informationen über diesen Prozess finden Sie unter [Hosten und Verwenden von WCF\-Diensten](http://go.microsoft.com/fwlink/?LinkId=99932) \(Seite ist möglicherweise nur in englischer Sprache verfügbar\).  
  
 Eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstbibliothek kann wie jeder andere [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst bereitgestellt werden.Beachten Sie jedoch, dass [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] die Konfiguration für DLLs nicht unterstützt.<xref:System.Configuration> unterstützt eine Konfigurationsdatei pro Anwendungsdomäne.Das [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienstbibliotheksprojekt umgeht diese Beschränkung, indem es während der Entwicklung die Datei app.config für die Bibliothek bereitstellt.Die Datei app.config wird nach der Bereitstellung jedoch nicht erkannt.  
  
 Sie müssen den Konfigurationscode in die von der Hostumgebung erkannte Konfigurationsdatei ziehen.Für das Selbsthosting sollten Sie den Inhalt der Datei app.config in die Datei app.config der ausführbaren Hostingdatei kopieren.Wenn Sie IIS zum Hosten Ihres Diensts einsetzen, sollten Sie den Inhalt der Datei app.config in die Datei web.config des virtuellen Verzeichnisses kopieren.