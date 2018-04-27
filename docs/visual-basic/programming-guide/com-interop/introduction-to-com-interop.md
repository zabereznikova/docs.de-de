---
title: Einführung in COM-Interop (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5a13fabd729218dc2a980b9c63e153d17a140cce
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="introduction-to-com-interop-visual-basic"></a>Einführung in COM-Interop (Visual Basic)
Das Component Object Model (COM) können ein Objekt, dessen Funktionalität mit anderen Komponenten und zum Hosten von Anwendungen verfügbar zu machen. COM-Objekte für das Windows-Programmierung für viele Jahre grundlegender Wichtigkeit wurden, Wiederherstellungsfunktionen Anwendungen für die common Language Runtime (CLR) bietet zahlreiche Vorteile.  
  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendungen werden schließlich die bei COM entwickelt ersetzen Bis dahin müssen Sie möglicherweise verwenden oder COM-Objekte mithilfe von Visual Studio erstellen. COM-Interoperabilität oder *COM-Interop*, können Sie vorhandenen COM-Objekte verwenden, beim Übergang in den [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] in Ihrem eigenen Tempo.  
  
 Mithilfe der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] um COM-Komponenten zu erstellen, können Sie COM-Interop ohne Registrierung. Dadurch können Sie steuern, welche DLL-Version aktiviert ist, wenn mehr als eine Version, die auf einem Computer installiert ist, und Endbenutzer verwenden Sie XCOPY oder FTP, kopieren Sie die Anwendung in ein geeignetes Verzeichnis auf ihrem Computer, in dem sie ausgeführt werden kann. Weitere Informationen finden Sie unter [-COM-Interop ohne Registrierung](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd).  
  
## <a name="managed-code-and-data"></a>Verwalteter Code und Daten  
 Entwickelter Code für die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] die Verfügbarkeitsklasse *verwaltetem Code*, und enthält Metadaten, die von der CLR verwendet wird. Vom verwendeten Daten [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendungen heißt *verwalteten Daten* da die Laufzeit datenbezogene Aufgaben verwaltet, wie z. B. Überprüfung Geben Sie reservieren und Freigeben von Arbeitsspeicher und ausführen. Standardmäßig Visual Basic .NET verwendet verwalteten Code und Daten, jedoch können Sie zugreifen, die nicht verwalteten Code und die Daten von COM-Objekten, die mithilfe von Interop-Assemblys (weiter unten auf dieser Seite beschrieben).  
  
## <a name="assemblies"></a>Assemblys  
 Eine Assembly ist der primäre Baustein einer [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendung. Es ist eine Auflistung von Funktionen, die erstellt, mit Versionsangabe und bereitgestellten als eine einzelne Implementierungseinheit, die eine oder mehrere Dateien enthält. Jede Assembly enthält ein Assemblymanifest.  
  
## <a name="type-libraries-and-assembly-manifests"></a>Typbibliotheken und Manifesten  
 Typbibliotheken werden die Merkmale von COM-Objekten, z. B. die Namen und Datentypen beschrieben. Assemblymanifesten führen dieselbe Funktion für [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendungen. Dazu zählen folgende Informationen:  
  
-   Assemblyidentität, Version, Kultur und digitale Signatur.  
  
-   Dateien, die die Implementierung der Assembly bilden.  
  
-   Typen und Ressourcen, die die Assembly bilden. Dazu gehören diejenigen, die daraus exportiert werden.  
  
-   Zeitpunkt der Kompilierung Abhängigkeiten von anderen Assemblys.  
  
-   Für die Assembly für die ordnungsgemäße Ausführung erforderlichen Berechtigungen.  
  
 Weitere Informationen zu Assemblys und Manifesten finden Sie unter [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
### <a name="importing-and-exporting-type-libraries"></a>Importieren und Exportieren von Typbibliotheken  
 Visual Studio enthält das Dienstprogramm Tlbimp, mit dem Sie Informationen aus einer Typbibliothek in importieren kann eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendung. Mithilfe des Hilfsprogramms Tlbexp können Sie Typbibliotheken von Assemblys generieren.  
  
 Informationen zu Tlbimp und Tlbexp finden Sie unter [Tlbimp.exe (Type Library Importer-Tool)](../../../framework/tools/tlbimp-exe-type-library-importer.md) und [Tlbexp.exe (Type Library Exporter-Tool)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d).  
  
## <a name="interop-assemblies"></a>Interop-Assemblys  
 Interop-Assemblys sind [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys, die Brücke zwischen verwaltetem und nicht verwaltetem code, Zuordnung COM-Objektmember in entsprechende [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Elemente verwaltet. Interop-Assemblys von Visual Basic .NET erstellt behandeln viele Details der Arbeit mit COM-Objekte, z. B. Interop-Marshalling.  
  
## <a name="interoperability-marshaling"></a>Interop-Marshalling  
 Alle [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendungen einen gemeinsamen Satz von gemeinsamen Typen, die Interoperabilität von Objekten, unabhängig von der Programmiersprache Ihrer Wahl zu ermöglichen, die verwendet wird. Die Parameter und Rückgabewerte von COM-Objekten verwenden manchmal Datentypen, die unterscheiden sich von denjenigen, die in verwaltetem Code verwendet. *Interop-Marshalling* versteht man Packaging-Parametern und Rückgabewerten in äquivalente Datentypen, wie sie zu und von COM-Objekte verschieben. Weitere Informationen finden Sie unter [Interop-Marshalling](../../../framework/interop/interop-marshaling.md).  
  
## <a name="see-also"></a>Siehe auch  
 [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Interoperabilität mit nicht verwaltetem Code](../../../framework/interop/index.md)  
 [Problembehandlung bei der Interoperabilität](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [Assemblys und der globale Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Tlbimp.exe (Type Library Importer-Tool)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe (Type Library Exporter-Tool)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [Interop Marshaling (Interop-Marshalling)](../../../framework/interop/interop-marshaling.md)  
 [COM-Interop ohne Registrierung](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)
