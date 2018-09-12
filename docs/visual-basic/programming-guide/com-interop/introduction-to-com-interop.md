---
title: Einführung in COM-Interop (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
ms.openlocfilehash: 5e31bfafdc321bb514ecdadd49b7e2c6adf53948
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44511694"
---
# <a name="introduction-to-com-interop-visual-basic"></a>Einführung in COM-Interop (Visual Basic)
Das Component Object Model (COM) können ein Objekt, das die Funktionen an andere Komponenten und hostanwendungen verfügbar zu machen. COM-Objekte für die Windows-Programmierung seit vielen Jahren von grundlegender Wichtigkeit waren bieten für die common Language Runtime (CLR) entwickelte Anwendungen zahlreiche Vorteile.  
  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendungen werden letztlich mit COM entwickelte ersetzt Bis dahin müssen Sie möglicherweise verwenden oder COM-Objekte mithilfe von Visual Studio erstellen. COM-Interoperabilität oder *COM-Interop*, können Sie vorhandenen COM-Objekte verwenden, bei der Umsetzung in den [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] in Ihrem eigenen Tempo.  
  
 Mithilfe der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] um COM-Komponenten zu erstellen, Sie können COM-Interop ohne Registrierung verwenden. Dies können Sie steuern, welche DLL-Version aktiviert ist, wenn mehr als eine Version, die auf einem Computer installiert ist, und Endbenutzer, verwenden Sie XCOPY oder FTP, kopieren Sie die Anwendung in ein geeignetes Verzeichnis auf ihrem Computer, in dem sie ausgeführt werden kann. Weitere Informationen finden Sie unter [-COM-Interop ohne Registrierung](../../../framework/interop/registration-free-com-interop.md).  
  
## <a name="managed-code-and-data"></a>Verwalteter Code und Daten  
 Code entwickelt wird, für die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] genannt *von verwaltetem Code*, und enthält Metadaten, die von der CLR verwendet wird. Vom verwendeten Daten [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendungen heißt *verwalteten Daten* , da die Laufzeit datenbezogene Aufgaben verwaltet, wie z. B. typüberprüfung, zuordnen und Freigeben von Arbeitsspeicher und ausführen. Standardmäßig Visual Basic .NET verwendet wird, verwalteten Code und Daten, aber Sie können den nicht verwalteten Code und Daten von COM-Objekten, die mithilfe von Interop-Assemblys (weiter unten auf dieser Seite beschrieben) zugreifen.  
  
## <a name="assemblies"></a>Assemblys  
 Eine Assembly ist der wichtigste Baustein einer [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendung. Es ist eine Sammlung von Funktionen, die erstellt, mit Versionsangabe und bereitgestellten als eine einzelne Implementierung-Einheit, die eine oder mehrere Dateien enthält. Jede Assembly enthält ein Assemblymanifest.  
  
## <a name="type-libraries-and-assembly-manifests"></a>Typbibliotheken und Manifesten  
 Typbibliotheken werden die Merkmale von COM-Objekten, z. B. Membernamen und Datentypen beschrieben. Manifesten führen dieselbe Funktion für [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendungen. Dazu gehören die folgenden Informationen:  
  
-   Assembly-ID, Version, Kultur und digitale Signatur.  
  
-   Dateien, aus denen die Implementierung der Assembly besteht.  
  
-   Typen und Ressourcen, die die Assembly bilden. Dies schließt die daraus exportiert werden.  
  
-   Während der Kompilierung Abhängigkeiten von anderen Assemblys.  
  
-   Berechtigungen für die Assembly für die ordnungsgemäße Ausführung erforderlich.  
  
 Weitere Informationen zu Assemblys und Manifesten finden Sie unter [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
### <a name="importing-and-exporting-type-libraries"></a>Importieren und Exportieren von Typbibliotheken  
 Visual Studio enthält das Dienstprogramm "Tlbimp", mit der Sie die Informationen aus einer Typbibliothek in importieren kann eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendung. Sie können mithilfe des Hilfsprogramms Tlbexp Typbibliotheken aus Assemblys generieren.  
  
 Weitere Informationen über "Tlbimp" und Tlbexp, finden Sie unter [Tlbimp.exe (Type Library Importer-Tool)](../../../framework/tools/tlbimp-exe-type-library-importer.md) und [Tlbexp.exe (Type Library Exporter-Tool)](../../../framework/tools/tlbexp-exe-type-library-exporter.md).  
  
## <a name="interop-assemblies"></a>Interop-Assemblys  
 Interop-Assemblys sind [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys, die Brücke zwischen verwaltetem und nicht verwaltetem code, die Member der Zuordnung COM-Objekts in entsprechende [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verwalteten Mitglieder. Interop-Assemblys, die von Visual Basic .NET erstellten behandeln viele der Details für die Arbeit mit COM-Objekte, z. B. Interop-Marshalling.  
  
## <a name="interoperability-marshaling"></a>Interop-Marshalling  
 Alle [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Anwendungen einen gemeinsamen Satz von häufig verwendeten Typen, die Interoperabilität von Objekten, unabhängig von der Programmiersprache zu ermöglichen, die verwendet wird. Die Parameter und Rückgabewerte von COM-Objekten verwenden manchmal Datentypen, die in verwaltetem Code verwendet unterscheiden. *Interop-Marshalling* versteht man das Zusammenfassen von Parametern und Rückgabewerten in äquivalente Datentypen, wie sie zu und von COM-Objekte verschieben. Weitere Informationen finden Sie unter [Interop-Marshalling](../../../framework/interop/interop-marshaling.md).  
  
## <a name="see-also"></a>Siehe auch

- [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
- [Exemplarische Vorgehensweise: Implementieren der Vererbung mit COM-Objekten](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
- [Interoperabilität mit nicht verwaltetem Code](../../../framework/interop/index.md)  
- [Problembehandlung bei der Interoperabilität](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
- [Assemblys und der globale Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
- [Tlbimp.exe (Type Library Importer-Tool)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
- [Tlbexp.exe (Type Library Exporter-Tool)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)  
- [Interop Marshaling (Interop-Marshalling)](../../../framework/interop/interop-marshaling.md)  
- [COM-Interop ohne Registrierung](../../../framework/interop/registration-free-com-interop.md)
