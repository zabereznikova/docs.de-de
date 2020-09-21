---
title: Importieren einer Typbibliothek als Assembly
description: Importieren Sie eine Typbibliothek, die COM-Typdefinitionen enthält, als Assembly. Erfahren Sie, wie Sie Metadaten anhand einer Typbibliothek erstellen, was in einer Interopassembly resultiert.
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
ms.openlocfilehash: bc1b921fea5aff086e21c046369f1d461f553bc7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554683"
---
# <a name="importing-a-type-library-as-an-assembly"></a>Importieren einer Typbibliothek als Assembly

Definitionen von COM-Typen befinden sich in der Regel in einer Typbibliothek. Im Gegensatz dazu erzeugen CLS-kompatible Compiler Typmetadaten in einer Assembly. Die zwei Quellen von Typinformationen sind sehr unterschiedlich. In diesem Thema werden Techniken zum Generieren von Metadaten aus einer Typbibliothek beschrieben. Die sich ergebende Assembly wird Interop-Assembly genannt, und die darin enthaltenen Typinformationen erlauben .NET Framework-Anwendungen die Verwendung von COM-Typen.

Es gibt zwei Möglichkeiten, um diese Typinformationen für Ihre Anwendung verfügbar zu machen:

- Mithilfe der Interopassemblys, die nur zur Entwurfszeit verwendet werden: Ab .NET Framework 4 können Sie den Compiler anweisen, die Typinformationen aus der Interopassembly in die ausführbare Datei einzubetten. Der Compiler bettet nur die Typinformationen ein, die Ihre Anwendung verwendet. Sie müssen die Interop-Assembly nicht mit Ihrer Anwendung bereitstellen. Dies ist das empfohlene Verfahren.

- Bereitstellen von Interopassemblys: So können Sie einen Standardverweis auf eine Interopassembly erstellen. In diesem Fall muss die Interop-Assembly mit Ihrer Anwendung bereitgestellt werden. Wenn Sie dieses Verfahren ohne eine private COM-Komponente verwenden, verweisen Sie immer auf die primäre Interop-Assembly (PIA), die vom Autor der COM-Komponente veröffentlicht wurde, die Sie in Ihren verwalteten Code einbetten möchten. Weitere Informationen zum Erstellen und Verwenden von primären Interop-Assemblys finden Sie unter [Primäre Interop-Assemblys](/previous-versions/dotnet/netframework-4.0/aax7sdch(v=vs.100)).

Wenn Sie Interop-Assemblys nur zur Entwurfszeit verwenden, können Sie Typinformationen aus der primären Interop-Assembly einbetten, die vom Autor der COM-Komponente veröffentlicht wurden. Sie müssen jedoch die primäre Interop-Assembly nicht mit Ihrer Anwendung bereitstellen.

Das Verwenden von Interop-Assemblys nur zur Entwurfszeit reduziert die Größe Ihrer Anwendung, da die meisten Anwendungen nicht alle Funktionen einer COM-Komponente verwenden. Der Compiler ist sehr effizient, wenn er Typinformationen einbettet. Wenn Ihre Anwendung nur einige der Methoden auf einer COM-Schnittstelle verwendet, bettet der Compiler die nicht verwendeten Methoden nicht ein. Wenn eine Anwendung mit eingebetteten Typinformationen mit einer anderen Anwendung dieser Art oder mit einer Anwendung interagiert, die eine primäre Interop-Assembly verwendet, nutzt die Common Language Runtime Typäquivalenzregeln, um zu bestimmen, ob zwei Typen mit dem gleichen Namen denselben COM-Typ darstellen. Sie müssen diese Regeln nicht kennen, um COM-Objekte zu verwenden. Wenn Sie jedoch an diesen Regeln interessiert sind, finden Sie weitere Informationen unter [Type Equivalence and Embedded Interop Types (Typäquivalenz und eingebettete Interop-Typen)](type-equivalence-and-embedded-interop-types.md).

## <a name="generating-metadata"></a>Generieren von Metadaten

Bei COM-Typbibliotheken kann es sich um eigenständige Dateien handeln, die die Erweiterung „.tlb“ (z.B. „Loanlib.tlb“) aufweisen. Einige Typbibliotheken werden im Ressourcenabschnitt einer DLL- oder EXE-Datei eingebettet. Andere Quellen von Typbibliotheksinformationen sind OLB- und OCX-Dateien.

Nachdem Sie die Typbibliothek gesucht haben, die die Implementierung des Ziel-COM-Typs enthält, haben Sie die folgenden Optionen zum Generieren einer Interop-Assembly, die Typmetadaten enthält:

- Visual Studio

  Visual Studio konvertiert COM-Typen automatisch in einer Typbibliothek in Metadaten in einer Assembly. Anweisungen hierzu finden Sie unter [Vorgehensweise: Add References to Type Libraries (Vorgehensweise: Hinzufügen von Verweisen zu Typbibliotheken)](how-to-add-references-to-type-libraries.md).

- [Tlbimp.exe (Type Library Importer-Tool)](../tools/tlbimp-exe-type-library-importer.md)

  Das Type Library Importer-Tool stellt Befehlszeilenoptionen zum Anpassen von Metadaten in der resultierenden Interop-Datei zur Verfügung, importiert Typen aus einer vorhandenen Typbibliothek und generiert eine Interop-Assembly und einen Namespace. Anweisungen hierzu finden Sie unter [Vorgehensweise: Generieren von Interopassemblys aus Typbibliotheken](how-to-generate-interop-assemblies-from-type-libraries.md).

- <xref:System.Runtime.InteropServices.TypeLibConverter?displayProperty=nameWithType>-Klasse

  Diese Klasse stellt Methoden zum Konvertieren von Co-Klassen und Schnittstellen in einer Typbibliothek in Metadaten in einer Assembly bereit. Sie erzeugt dieselbe Metadatenausgabe wie „Tlbimp.exe“. Anders als bei „Tlbimp.exe“, kann die <xref:System.Runtime.InteropServices.TypeLibConverter>-Klasse eine In-Memory-Typbibliothek in Metadaten konvertieren.

- Benutzerdefinierte Wrapper

  Wenn eine Typbibliothek falsch oder nicht verfügbar ist, ist eine Option das Erstellen einer doppelten Definition der Klasse oder Schnittstelle in verwaltetem Quellcode. Anschließend kompilieren Sie den Quellcode mit einem Compiler, der die Runtime zur Erstellung von Metadaten in einer Assembly anzielt.

  Um COM-Typen manuell zu definieren, benötigen Sie Zugriff auf die folgenden Elemente:

  - Genaue Beschreibungen der Co-Klassen und -Schnittstellen, die definiert werden.

  - Einen Compiler, z.B. den C#-Compiler, der die entsprechenden .NET Framework-Klassendefinitionen generieren kann.

  - Kenntnisse der Konvertierungsregeln einer Typbibliothek in eine Assembly.

  Das Schreiben eines benutzerdefinierten Wrappers ist ein erweitertes Verfahren. Weitere Informationen zum Generieren von benutzerdefinierten Wrappern finden Sie unter [Anpassen von Standardwrappern](/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100)).

 Weitere Informationen zum COM-Interop-Importvorgang finden Sie unter [Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100)).

## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.TypeLibConverter>
- [Verfügbarmachen von COM-Komponenten für .NET Framework](exposing-com-components.md)
- [Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))
- [Tlbimp.exe (Type Library Importer-Tool)](../tools/tlbimp-exe-type-library-importer.md)
- [Anpassen von Standardwrappern](/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))
- [Verwenden von COM-Typen in verwaltetem Code](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))
- [Kompilieren eines Interop-Projekts](compiling-an-interop-project.md)
- [Bereitstellen einer Interop-Anwendung](deploying-an-interop-application.md)
- [How to: Hinzufügen von Verweisen zu Typbibliotheken](how-to-add-references-to-type-libraries.md)
- [How to: Generieren von Interopassemblys aus Typbibliotheken](how-to-generate-interop-assemblies-from-type-libraries.md)
