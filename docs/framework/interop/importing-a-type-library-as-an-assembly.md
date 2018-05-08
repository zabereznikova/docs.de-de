---
title: Importieren einer Typbibliothek als Assembly
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- type metadata
- custom wrappers
- metadata
- exposing COM components to .NET Framework
- Type Library Importer
- interoperation with unmanaged code, importing type library
- interoperation with unmanaged code, exposing COM components
- type libraries
- TypeLibConverter class, importing type library as assembly
- COM interop, importing type library
- COM interop, exposing COM components
ms.assetid: d1898229-cd40-426e-a275-f3eb65fbc79f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89479ca4a41f761d4aacaf6d8d962bfba62be811
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="importing-a-type-library-as-an-assembly"></a>Importieren einer Typbibliothek als Assembly
Definitionen von COM-Typen befinden sich in der Regel in einer Typbibliothek. Im Gegensatz dazu erzeugen CLS-kompatible Compiler Typmetadaten in einer Assembly. Die zwei Quellen von Typinformationen sind sehr unterschiedlich. In diesem Thema werden Techniken zum Generieren von Metadaten aus einer Typbibliothek beschrieben. Die sich ergebende Assembly wird Interop-Assembly genannt, und die darin enthaltenen Typinformationen erlauben .NET Framework-Anwendungen die Verwendung von COM-Typen.  
  
 Es gibt zwei Möglichkeiten, um diese Typinformationen für Ihre Anwendung verfügbar zu machen:  
  
-   Mithilfe der Interop-Typen, die nur zur Entwurfszeit verwendet werden: Beginnend mit der [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], können Sie den Compiler anweisen, die Typinformationen aus einer Interop-Assembly in der ausführbaren Datei einzubetten. Der Compiler bettet nur die Typinformationen ein, die Ihre Anwendung verwendet. Sie müssen die Interop-Assembly nicht mit Ihrer Anwendung bereitstellen. Dies ist das empfohlene Verfahren.  
  
-   Durch die Bereitstellung von Interop-Assemblys können Sie einen Standardverweis auf eine Interop-Assembly erstellen. In diesem Fall muss die Interop-Assembly mit Ihrer Anwendung bereitgestellt werden. Wenn Sie dieses Verfahren ohne eine private COM-Komponente verwenden, verweisen Sie immer auf die primäre Interop-Assembly (PIA), die vom Autor der COM-Komponente veröffentlicht wurde, die Sie in Ihren verwalteten Code einbetten möchten. Weitere Informationen zum Erstellen und Verwenden von primären Interop-Assemblys finden Sie unter [Primäre Interop-Assemblys](https://msdn.microsoft.com/library/b977a8be-59a0-40a0-a806-b11ffba5c080(v=vs.100)).  
  
 Wenn Sie Interop-Assemblys nur zur Entwurfszeit verwenden, können Sie Typinformationen aus der primären Interop-Assembly einbetten, die vom Autor der COM-Komponente veröffentlicht wurden. Sie müssen jedoch die primäre Interop-Assembly nicht mit Ihrer Anwendung bereitstellen.  
  
 Das Verwenden von Interop-Assemblys nur zur Entwurfszeit reduziert die Größe Ihrer Anwendung, da die meisten Anwendungen nicht alle Funktionen einer COM-Komponente verwenden. Der Compiler ist sehr effizient, wenn er Typinformationen einbettet. Wenn Ihre Anwendung nur einige der Methoden auf einer COM-Schnittstelle verwendet, bettet der Compiler die nicht verwendeten Methoden nicht ein. Wenn eine Anwendung mit eingebetteten Typinformationen mit einer anderen Anwendung dieser Art oder mit einer Anwendung interagiert, die eine primäre Interop-Assembly verwendet, nutzt die Common Language Runtime Typäquivalenzregeln, um zu bestimmen, ob zwei Typen mit dem gleichen Namen denselben COM-Typ darstellen. Sie müssen diese Regeln nicht kennen, um COM-Objekte zu verwenden. Wenn Sie jedoch an diesen Regeln interessiert sind, finden Sie weitere Informationen unter [Type Equivalence and Embedded Interop Types (Typäquivalenz und eingebettete Interop-Typen)](../../../docs/framework/interop/type-equivalence-and-embedded-interop-types.md).  
  
## <a name="generating-metadata"></a>Generieren von Metadaten  
 Bei COM-Typbibliotheken kann es sich um eigenständige Dateien handeln, die die Erweiterung „.tlb“ (z.B. „Loanlib.tlb“) aufweisen. Einige Typbibliotheken werden im Ressourcenabschnitt einer DLL- oder EXE-Datei eingebettet. Andere Quellen von Typbibliotheksinformationen sind OLB- und OCX-Dateien.  
  
 Nachdem Sie die Typbibliothek gesucht haben, die die Implementierung des Ziel-COM-Typs enthält, haben Sie die folgenden Optionen zum Generieren einer Interop-Assembly, die Typmetadaten enthält:  
  
-   Visual Studio  
  
     Visual Studio konvertiert COM-Typen automatisch in einer Typbibliothek in Metadaten in einer Assembly. Anweisungen hierzu finden Sie unter [How to: Add References to Type Libraries (Vorgehensweise: Hinzufügen von Verweisen zu Typbibliotheken)](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md) und [Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100)).  
  
-   [Tlbimp.exe (Type Library Importer-Tool)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
  
     Das Type Library Importer-Tool stellt Befehlszeilenoptionen zum Anpassen von Metadaten in der resultierenden Interop-Datei zur Verfügung, importiert Typen aus einer vorhandenen Typbibliothek und generiert eine Interop-Assembly und einen Namespace. Weitere Informationen finden Sie unter [How to: Generate Interop Assemblies from Type Libraries (Vorgehensweise: Generieren von Interop-Assemblys aus Typbibliotheken)](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).  
  
-   <xref:System.Runtime.InteropServices.TypeLibConverter?displayProperty=nameWithType>-Klasse  
  
     Diese Klasse stellt Methoden zum Konvertieren von Co-Klassen und Schnittstellen in einer Typbibliothek in Metadaten in einer Assembly bereit. Sie erzeugt dieselbe Metadatenausgabe wie „Tlbimp.exe“. Anders als bei „Tlbimp.exe“, kann die <xref:System.Runtime.InteropServices.TypeLibConverter>-Klasse eine In-Memory-Typbibliothek in Metadaten konvertieren.  
  
-   Benutzerdefinierte Wrapper  
  
     Wenn eine Typbibliothek falsch oder nicht verfügbar ist, ist eine Option das Erstellen einer doppelten Definition der Klasse oder Schnittstelle in verwaltetem Quellcode. Anschließend kompilieren Sie den Quellcode mit einem Compiler, der die Runtime zur Erstellung von Metadaten in einer Assembly anzielt.  
  
     Um COM-Typen manuell zu definieren, benötigen Sie Zugriff auf die folgenden Elemente:  
  
    -   Genaue Beschreibungen der Co-Klassen und -Schnittstellen, die definiert werden.  
  
    -   Einen Compiler, z.B. den C#-Compiler, der die entsprechenden .NET Framework-Klassendefinitionen generieren kann.  
  
    -   Kenntnisse der Konvertierungsregeln einer Typbibliothek in eine Assembly.  
  
     Das Schreiben eines benutzerdefinierten Wrappers ist ein erweitertes Verfahren. Weitere Informationen zum Generieren von benutzerdefinierten Wrappern finden Sie unter [Anpassen von Standardwrappern](https://msdn.microsoft.com/library/c40d089b-6a3c-41b5-a20d-d760c215e49d(v=vs.100)).  
  
 Weitere Informationen zum COM-Interop-Importvorgang finden Sie unter [Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](https://msdn.microsoft.com/library/bf3f90c5-4770-4ab8-895c-3ba1055cc958(v=vs.100)).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.TypeLibConverter>  
 [Verfügbarmachen von COM-Komponenten für .NET Framework](../../../docs/framework/interop/exposing-com-components.md)  
 [Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](https://msdn.microsoft.com/library/bf3f90c5-4770-4ab8-895c-3ba1055cc958(v=vs.100))  
 [Tlbimp.exe (Type Library Importer-Tool)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
 [Anpassen von Standardwrappern](https://msdn.microsoft.com/library/c40d089b-6a3c-41b5-a20d-d760c215e49d(v=vs.100))  
 [Verwenden von COM-Typen in verwaltetem Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))  
 [Kompilieren eines Interop-Projekts](../../../docs/framework/interop/compiling-an-interop-project.md)  
 [Bereitstellen einer Interop-Anwendung](../../../docs/framework/interop/deploying-an-interop-application.md)  
 [Gewusst wie: Hinzufügen von Verweisen zu Typbibliotheken](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md)  
 [Gewusst wie: Generieren von Interop-Assemblys aus Typbibliotheken](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md)  
 [Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))
