---
title: "Einführung in COM-Interop (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- interop assemblies
- COM interop, about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8866dbadca040c57ed2b59540dd2c341eb81758c
ms.lasthandoff: 03/13/2017

---
# <a name="introduction-to-com-interop-visual-basic"></a>Einführung in COM-Interop (Visual Basic)
Das Component Object Model (COM) können ein Objekt seine Funktionalität an andere Komponenten und zum Hosten von Anwendungen verfügbar zu machen. Während COM-Objekte für Windows-Programmierung seit vielen Jahren wurden, bieten für die common Language Runtime (CLR) entwickelte Anwendungen zahlreiche Vorteile.  
  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]Anwendung werden schließlich entwickelte mit COM ersetzen Bis dahin müssen unter Umständen verwenden oder Erstellen von COM-Objekte mithilfe von [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]. COM-Interoperabilität oder *COM-Interop*, können Sie vorhandene COM-Objekte verwenden, beim Übergang in den [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] in Ihrem eigenen Tempo.  
  
 Mithilfe der [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] um COM-Komponenten zu erstellen, können Sie COM-Interop ohne Registrierung. Dadurch können Sie steuern, welche DLL-Version aktiviert ist, wenn mehrere Versionen auf einem Computer installiert ist, und Endbenutzer verwenden Sie XCOPY oder FTP, kopieren Sie die Anwendung in ein geeignetes Verzeichnis auf ihrem Computer, in dem sie ausgeführt werden kann. Weitere Informationen finden Sie unter [-COM-Interop ohne Registrierung](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd).  
  
## <a name="managed-code-and-data"></a>Verwalteter Code und Daten  
 Entwickelter Code für die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] genannt wird *verwaltetem Code*, und enthält Metadaten, die von CLR verwendet wird. Daten, die von [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Applikationen aufgerufen *verwaltet Daten* da die Laufzeit datenbezogene Aufgaben verwaltet, wie z. B. reservieren und Freigeben von Arbeitsspeicher und Durchführung von Prüfung geben. In der Standardeinstellung [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] verwendet verwalteten Code und Daten, aber Sie können verwalteten Code und Daten von COM-Objekten, die mithilfe von Interop-Assemblys (siehe unten auf dieser Seite) zugreifen.  
  
## <a name="assemblies"></a>Assemblys  
 Eine Assembly ist der wichtigste Baustein einer [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Anwendung. Es ist eine Auflistung von Funktionen, die erstellt, mit Versionsangabe und bereitgestellten als eine einzelne Implementierungseinheit, die eine oder mehrere Dateien enthält. Jede Assembly enthält ein Assemblymanifest.  
  
## <a name="type-libraries-and-assembly-manifests"></a>Typbibliotheken und Assemblymanifeste  
 Typbibliotheken beschreiben Merkmale von COM-Objekten, z. B. Membernamen und Datentypen. Assemblymanifeste führen dieselbe Funktion für [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Applications. Dazu zählen folgende Informationen:  
  
-   Assemblyidentität, Version, Kultur und digitale Signatur.  
  
-   Dateien, die die Implementierung der Assembly bilden.  
  
-   Typen und Ressourcen, die die Assembly bilden. Dies gilt für die von ihr exportiert werden.  
  
-   Während der Kompilierung Abhängigkeiten von anderen Assemblys.  
  
-   Für die ordnungsgemäße Ausführung der Assembly erforderlichen Berechtigungen.  
  
 Weitere Informationen zu Assemblys und Manifesten finden Sie unter [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
### <a name="importing-and-exporting-type-libraries"></a>Importieren und Exportieren von Typbibliotheken  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]enthält das Dienstprogramm Tlbimp, mit dem Sie Informationen aus einer Typbibliothek in importieren kann eine [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Anwendung. Sie können Typbibliotheken von Assemblys generieren, indem Sie mit dem Dienstprogramm Tlbexp.  
  
 Informationen über Tlbimp und Tlbexp finden Sie unter [Tlbimp.exe (Type Library Importer)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) und [Tlbexp.exe (Type Library Exporter)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d).  
  
## <a name="interop-assemblies"></a>Interop-Assemblys  
 Interop-Assemblys sind [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Assemblys, die Brücke zwischen verwaltetem und nicht verwaltetem code, Zuordnung COM-Objektmember den entsprechenden [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Elemente verwaltet. Interop-Assemblys erstellt, indem [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] behandeln viele Einzelheiten der Arbeit mit COM-Objekten, z. B. Interop-Marshalling.  
  
## <a name="interoperability-marshaling"></a>Interop-Marshalling  
 Alle [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Applikationen verfügen über allgemeine Typen, die Interoperabilität von Objekten, unabhängig von der Programmiersprache zu ermöglichen, die verwendet wird. Die Parameter und Rückgabewerte von COM-Objekten verwenden manchmal Datentypen, die in verwaltetem Code verwendet unterscheiden. *Interop-Marshalling* als wird das Zusammenfassen von Parametern und Rückgabewerten in äquivalente Datentypen übergeben an und von COM-Objekten bezeichnet. Weitere Informationen finden Sie unter [Interop-Marshalling](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a).  
  
## <a name="see-also"></a>Siehe auch  
 [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Interoperation mit nicht verwaltetem Code](https://msdn.microsoft.com/library/sd10k43k)   
 [Problembehandlung bei der Interoperabilität](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)   
 [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Tlbimp.exe (Type Library Importer-Tool)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)   
 [Tlbexp.exe (Type Library Exporter-Tool)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)   
 [Interop-Marshalling](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a)   
 [Registration-Free COM-Interop](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)
