---
title: "Importing a Type Library as an Assembly | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "importing type library"
  - "type metadata"
  - "custom wrappers"
  - "metadata"
  - "exposing COM components to .NET Framework"
  - "Type Library Importer"
  - "interoperation with unmanaged code, importing type library"
  - "interoperation with unmanaged code, exposing COM components"
  - "type libraries"
  - "TypeLibConverter class, importing type library as assembly"
  - "COM interop, importing type library"
  - "COM interop, exposing COM components"
ms.assetid: d1898229-cd40-426e-a275-f3eb65fbc79f
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Importing a Type Library as an Assembly
Definitionen von COM\-Typen befinden sich in der Regel in einer Typbibliothek.  Typmetadaten dagegen werden von CLS\-kompatiblen Compilern in einer Assembly erstellt.  Die beiden Typinformationsquellen unterscheiden sich wesentlich voneinander.  In diesem Abschnitt werden die Techniken zum Generieren von Metadaten aus einer Typbibliothek beschrieben.  Die resultierende Assembly wird als Interopassembly bezeichnet. Durch die in ihr enthaltenen Typinformationen können von .NET Framework\-Anwendungen COM\-Typen verwendet werden.  
  
 Diese Typinformationen können einer Anwendung auf zwei Arten bereitgestellt werden:  
  
-   Verwenden zur Entwurfszeit gültiger Interopassemblys: Indem Sie mit der [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]\-Anweisung beginnen, wird der Compiler angewiesen, Typinformationen von der Interopassembly in die EXE\-Datei einzubetten.  Der Compiler bettet nur die Typinformationen ein, die von der Anwendung verwendet werden.  Die Interopassembly muss nicht mit der Anwendung bereitgestellt werden.  Dies ist das empfohlene Verfahren.  
  
-   Bereitstellen von Interopassemblys: Sie können einen Standardverweis auf die Interopassembly erstellen.  In diesem Fall muss die Interopassembly mit der Anwendung bereitgestellt werden.  Wenn Sie dieses Verfahren und keine private COM\-Komponente verwenden, verweisen Sie immer auf die primäre Interopassembly \(Primary Interop Assembly, PIA\), die vom Verfasser der COM\-Komponente, die Sie in den verwalteten Code aufnehmen möchten, veröffentlicht wurde.  Weitere Informationen zum Erstellen und Verwenden von primären Interopassemblys finden Sie unter [Primäre Interopassemblys](http://msdn.microsoft.com/de-de/b977a8be-59a0-40a0-a806-b11ffba5c080).  
  
 Bei der Verwendung von nur zur Entwurfszeit gültigen Interopassemblys können Sie Typinformationen aus der primären Interopassembly einbetten, die vom Autor der COM\-Komponente veröffentlicht wurden.  Die primäre Interopassembly muss jedoch nicht mit der Anwendung bereitgestellt werden.  
  
 Durch die Verwendung von nur zur Entwurfszeit gültigen Interopassemblys wird die Größe der Anwendung reduziert, da von den meisten Anwendungen nicht alle Funktionen einer COM\-Komponente verwendet werden.  Der Compiler arbeitet bei der Einbettung von Typinformationen sehr effizient. Werden von der Anwendung nur einige der Methoden für eine COM\-Schnittstelle verwendet, werden die nicht verwendeten Methoden vom Compiler nicht eingebettet.  Bei der Interaktion einer Anwendung mit eingebetteten Typinformationen mit einer anderen Anwendung, in die Typinformationen eingebettet wurden, oder mit einer Anwendung, die eine primäre Interopassembly verwendet, werden von der Common Language Runtime zur Ermittlung, ob zwei Typen mit dem gleichen Namen den gleichen COM\-Typ darstellen, Typäquivalenzregeln verwendet.  Zur Verwendung von COM\-Objekten ist die Kenntnis dieser Regeln nicht erforderlich.  Möchten Sie trotzdem die Regeln einsehen, finden Sie sie unter [Type Equivalence and Embedded Interop Types](../../../docs/framework/interop/type-equivalence-and-embedded-interop-types.md).  
  
## Generieren von Metadaten  
 COM\-Typbibliotheken können eigenständige Dateien mit einer TLB\-Dateierweiterung sein, z. B. "Loanlib.tlb".  Einige Typbibliotheken werden in den Ressourcenabschnitt von DLL\- oder EXE\-Dateien eingebettet.  Weitere Quellen für Typbibliotheksinformationen sind OLB\-Dateien und OCX\-Dateien.  
  
 Nachdem Sie die Typbibliothek gefunden haben, die die Implementierung des COM\-Zieltyps enthält, stehen mehrere Optionen zum Generieren einer Interopassembly mit Typmetadaten zur Verfügung:  
  
-   Visual Studio  
  
     Mit Visual Studio können die COM\-Typen in einer Typbibliothek automatisch in Metadaten in einer Assembly konvertiert werden.  Entsprechende Anweisungen finden Sie unter [Gewusst wie: Hinzufügen von Verweisen zu Typbibliotheken](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md) und [Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office\-Assemblys](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
-   [Type Library Importer\-Tool \(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
  
     Die Metadaten in der resultierenden Interop\-Datei können mithilfe von Befehlzeilenoptionen des Typbibliothekimporters angepasst werden. Die Typen werden aus einer vorhandenen Typbibliothek importiert, und eine Interop\-Assembly und ein Namespace werden generiert.  Entsprechende Anweisungen finden Sie unter [Gewusst wie: Generieren von Interop\-Assemblys aus Typbibliotheken](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).  
  
-   <xref:System.Runtime.InteropServices.TypeLibConverter?displayProperty=fullName>\-Klasse  
  
     Von dieser Klasse werden Methoden für die Konvertierung von Co\-Klassen und Schnittstellen in einer Typbibliothek zu Metadaten in einer Assembly bereitgestellt.  Auf diese Weise werden die gleichen Metadaten ausgegeben wie bei der Verwendung von "Tlbimp.exe".  Im Unterschied zu "Tlbimp.exe" können von der <xref:System.Runtime.InteropServices.TypeLibConverter>\-Klasse allerdings Typbibliotheken im Arbeitsspeicher in Metadaten konvertiert werden.  
  
-   Benutzerdefinierte Wrapper  
  
     Wenn eine Typbibliothek nicht verfügbar oder inkorrekt ist, können Sie eine doppelte Definition der Klasse oder Schnittstelle im verwalteten Quellcode erstellen.  Anschließend kompilieren Sie den Quellcode mit einem Compiler, der Common Language Runtime als Ziel hat, sodass Metadaten in einer Assembly erstellt werden.  
  
     Um COM\-Typen manuell zu definieren, müssen Sie auf folgende Elemente zugreifen können:  
  
    -   Präzise Beschreibungen der zu definierenden Co\-Klassen und Schnittstellen.  
  
    -   Ein Compiler, z. B. ein C\#\-Compiler, mit dem Sie die entsprechenden .NET Framework\-Klassendefinitionen generieren können.  
  
    -   Kenntnis der Regeln für die Konvertierung von Typbibliotheken in Assemblys.  
  
     Das Schreiben eines benutzerdefinierten Wrappers ist ein fortgeschrittenes Verfahren.  Weitere Informationen zum Generieren von benutzerdefinierten Wrappern finden Sie unter [Anpassen von Standardwrappern](http://msdn.microsoft.com/de-de/c40d089b-6a3c-41b5-a20d-d760c215e49d).  
  
 Weitere Informationen zum Importiervorgang mit COM\-Interop finden Sie unter [Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](http://msdn.microsoft.com/de-de/bf3f90c5-4770-4ab8-895c-3ba1055cc958).  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.TypeLibConverter>   
 [Exposing COM Components to the .NET Framework](../../../docs/framework/interop/exposing-com-components.md)   
 [Type Library to Assembly Conversion Summary](http://msdn.microsoft.com/de-de/bf3f90c5-4770-4ab8-895c-3ba1055cc958)   
 [Tlbimp.exe \(Type Library Importer\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)   
 [Customizing Standard Wrappers](http://msdn.microsoft.com/de-de/c40d089b-6a3c-41b5-a20d-d760c215e49d)   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/de-de/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [Compiling an Interop Project](../../../docs/framework/interop/compiling-an-interop-project.md)   
 [Deploying an Interop Application](../../../docs/framework/interop/deploying-an-interop-application.md)   
 [How to: Add References to Type Libraries](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md)   
 [How to: Generate Interop Assemblies from Type Libraries](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md)   
 [Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office\-Assemblys](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)