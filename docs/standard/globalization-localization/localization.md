---
title: "Lokalisierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anwendungsentwicklung [.NET Framework], Lokalisierung"
  - "Codeblöcke"
  - "Kultur, Lokalisierung"
  - "Globale Anwendungen, Lokalisierung"
  - "Globalisierung [.NET Framework], Lokalisierung"
  - "Internationale Anwendungen [.NET Framework], Lokalisierung"
  - "Lokalisierung [.NET Framework], Informationen über die Lokalisierung"
  - "Lokalisieren von Ressourcen"
  - "Benutzeroberflächenblöcke"
  - "Weltweit einsatzfähige Anwendungen, Lokalisierung"
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Lokalisierung
Die Lokalisierung ist der Prozess der Übersetzung der Ressourcen einer Anwendung in lokalisierte Versionen für die einzelnen Kulturen, die von der Anwendung unterstützt werden sollen.  Mit dem Schritt der Lokalisierung sollten Sie erst beginnen, wenn Sie den Schritt zur Überprüfung der [Überprüfung der Lokalisierbarkeit](../../../docs/standard/globalization-localization/localizability-review.md), der sicherstellen soll, dass die globalisierte Anwendung für die Lokalisierung bereit ist, abgeschlossen haben.  
  
 Eine für die Lokalisierung bereite Anwendung ist in zwei konzeptuelle Blöcke unterteilt. Ein Block enthält alle Elemente der Benutzeroberfläche und der andere Block den ausführbaren Code.  Der Benutzeroberflächenblock enthält lediglich lokalisierbare Elemente der Benutzeroberfläche für die neutrale Kultur, z. B. Zeichenfolgen, Fehlermeldungen, Dialogfelder, Menüs, eingebettete Objektressourcen usw.  Der Codeblock enthält nur den Anwendungscode, der von allen unterstützten Kulturen verwendet werden kann.  Die Common Language Runtime unterstützt ein Satellitenassembly\-Ressourcenmodell, das den ausführbaren Code einer Anwendung von den Ressourcen trennt.  Weitere Informationen zum Implementieren dieses Modells finden Sie unter [Ressourcen in Desktop\-Apps](../../../docs/framework/resources/index.md).  
  
 Fügen Sie für jede lokalisierte Version der Anwendung eine neue Satellitenassembly hinzu, die den lokalisierten Benutzeroberflächenblock enthält, der in die entsprechende Sprache für die Zielkultur übersetzt ist.  Der Codeblock bleibt für sämtliche Kulturen identisch.  Die lokalisierte Version der Anwendung entsteht durch die Kombination der lokalisierten Version des Benutzeroberflächenblocks und des Codeblocks.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] unterstützt das Windows Forms Resource Editor\-Tool \(Winres.exe\), das eine schnelle Lokalisierung von Windows Forms für Zielkulturen ermöglicht.  Informationen zum Verwenden dieses Tools finden Sie unter [Winres.exe \(Windows Forms Resource Editor\)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).  
  
## Siehe auch  
 [Globalisierung und Lokalisierung](../../../docs/standard/globalization-localization/index.md)   
 [Überprüfung der Lokalisierbarkeit](../../../docs/standard/globalization-localization/localizability-review.md)   
 [Globalisierung](../../../docs/standard/globalization-localization/globalization.md)   
 [Ressourcen in Desktop\-Apps](../../../docs/framework/resources/index.md)