---
title: "Introduction to COM Interop (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "interop assemblies"
  - "COM interop, about COM interop"
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Introduction to COM Interop (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Mit COM \(Component Object Model\) kann ein Objekt seine Funktionen für andere Komponenten oder Hostanwendungen verfügbar machen.  Wenn auch COM\-Objekte lange Zeit wesentliche Bestandteile der Windows\-Programmierung waren, so bieten doch Anwendungen, die für die Common Language Runtime \(CLR\) entwickelt wurden, viele Vorteile.  
  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Anwendungen werden früher oder später Anwendungen ersetzen, die mit COM entwickelt wurden.  Bis dahin müssen Sie in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] COM\-Objekte erstellen bzw. verwenden.  COM\-Interoperabilität \(*COM\-Interop*\) ermöglicht das Verwenden vorhandener COM\-Objekte, bis Sie vollständig zu [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] übergegangen sind.  
  
 Mit [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] können Sie COM\-Interop ohne Registrierung zum Erstellen von COM\-Komponenten verwenden.  Wenn mehrere Versionen auf einem Computer installiert sind, können Sie damit steuern, welche DLL\-Version aktiviert wird. Außerdem können Endbenutzer Ihre Anwendung mit XCOPY oder FTP in das entsprechende Verzeichnis auf ihrem Computer kopieren und ausführen.  Weitere Informationen finden Sie unter [Registration\-Free COM Interop](../Topic/Registration-Free%20COM%20Interop.md).  
  
## Verwalteter Code und verwaltete Daten  
 Für [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] entwickelter Code wird als *verwalteter Code* bezeichnet und enthält Metadaten, die von CLR verwendet werden.  Die von [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Anwendungen verwendeten Daten werden als *verwaltete Daten* bezeichnet, da die Laufzeit datenbezogene Aufgaben verwaltet, z. B. das Belegen und Freigeben von Speicher oder die Typüberprüfung.  Standardmäßig verwendet [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] verwalteten Code und verwaltete Daten. Mithilfe von Interop\-Assemblys können Sie jedoch auf nicht verwalteten Code und nicht verwaltete Daten von COM\-Objekten zugreifen. Interop\-Assemblys werden weiter unten auf dieser Seite beschrieben.  
  
## Assemblys  
 Eine Assembly ist der wichtigste Baustein einer [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Anwendung.  Sie stellt eine Funktionalitätsauflistung dar, die erstellt, mit Versionsinformationen versehen und als einzelne Implementierungseinheit mit einer oder mehreren Dateien bereitgestellt wird.  Jede Assembly enthält ein Assemblymanifest.  
  
## Typbibliotheken und Assemblymanifeste  
 Typbibliotheken beschreiben Merkmale von COM\-Objekten, z. B. Membernamen und Datentypen.  Assemblymanifeste erfüllen die gleiche Funktion für [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Anwendungen.  Sie umfassen Informationen über Folgendes:  
  
-   Assemblyidentität, Version, Kultur und digitale Signatur  
  
-   Dateien der Assemblyimplementierung  
  
-   Typen und Ressourcen, aus denen die Assembly besteht.  Dazu gehören auch diejenigen, die von ihr exportiert werden.  
  
-   Abhängigkeiten von anderen Assemblys für die Kompilierungszeit  
  
-   Erforderliche Berechtigungen für die ordnungsgemäße Ausführung der Assembly  
  
 Weitere Informationen zu Assemblys und Assemblymanifesten finden Sie unter [Assemblys und der globale Assemblycache](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md).  
  
### Importieren und Exportieren von Typbibliotheken  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] enthält das Dienstprogramm Tlbimp, mit dem Sie Informationen aus einer Typbibliothek in eine [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Anwendung importieren können.  Mit dem Dienstprogramm Tlbexp können Sie Typbibliotheken von Assemblys generieren.  
  
 Informationen über die Dienstprogramme Tlbimp und Tlbexp finden Sie unter [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md) und [Tlbexp.exe \(Type Library Exporter\)](../Topic/Tlbexp.exe%20\(Type%20Library%20Exporter\).md).  
  
## Interop\-Assemblys  
 Interop\-Assemblys sind [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Assemblys, die als Brücke zwischen verwaltetem und nicht verwaltetem Code fungieren, indem sie COM\-Objektmember den entsprechenden verwalteten [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Membern zuordnen.  Von [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] erstellte Interop\-Assemblys behandeln viele Einzelheiten der Arbeit mit COM\-Objekten, z. B. Interoperabilitätsmarshalling.  
  
## Interoperabilitätsmarshalling  
 Alle [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Anwendungen verfügen gemeinsam über eine Reihe häufig verwendeter Typen, die unabhängig von der verwendeten Programmiersprache die Interoperabilität von Objekten ermöglichen.  Bei Parametern und Rückgabewerten von COM\-Objekten werden gelegentlich andere Datentypen verwendet als in verwaltetem Code.  Als *Interoperabilitätsmarshalling* wird das Zusammenfassen von Parametern und Rückgabewerten in äquivalente Datentypen beim Übergeben an und von COM\-Objekten bezeichnet.  Weitere Informationen finden Sie unter [Interop Marshaling](../Topic/Interop%20Marshaling.md).  
  
## Siehe auch  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Interoperating with Unmanaged Code](../Topic/Interoperating%20with%20Unmanaged%20Code.md)   
 [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)   
 [Assemblys und der globale Assemblycache](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)   
 [Tlbexp.exe \(Type Library Exporter\)](../Topic/Tlbexp.exe%20\(Type%20Library%20Exporter\).md)   
 [Interop Marshaling](../Topic/Interop%20Marshaling.md)   
 [Registration\-Free COM Interop](../Topic/Registration-Free%20COM%20Interop.md)