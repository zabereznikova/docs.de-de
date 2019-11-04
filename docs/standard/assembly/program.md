---
title: Programmieren mit Assemblys
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
ms.openlocfilehash: 9f07d36d9e47189d53e367fd1406e5684c024aa3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107057"
---
# <a name="program-with-assemblies"></a>Programmieren mit Assemblys
Assemblys sind die Bausteine von .NET Framework; sie bilden das Fundament für Bereitstellung, Versionskontrolle, Wiederverwendung, Gültigkeitsbereiche für die Aktivierung und Sicherheitsberechtigungen. Eine Assembly stellt der Common Language Runtime die Informationen zur Verfügung, die sie zum Erkennen der Typimplementierungen benötigt. Sie ist eine Auflistung von Typen und Ressourcen, die so erstellt wurden, dass sie zusammenarbeiten und eine logische funktionelle Einheit bilden. Für die Common Language Runtime sind Typen nur im Kontext einer Assembly vorhanden.  
  
 In diesem Abschnitt wird beschrieben, wie Module, Assembys aus Modulen und ein Schlüsselpaar erstellt werden, wie eine Assembly mit einem starken Namen signiert wird und wie eine Assembly im globalen Assemblycache installiert wird. Dieser Abschnitt beschreibt zusätzlich, wie Sie [MSIL Disassembler (Ildasm.exe)](../../framework/tools/ildasm-exe-il-disassembler.md) verwenden, um Informationen aus dem Assemblymanifest anzuzeigen.  
  
> [!NOTE]
> Ab der .NET Framework-Version 2.0 lädt die Runtime keine Assembly, die mit einer Version von .NET Framework kompiliert wurde, die eine höhere Versionsnummer als die aktuell geladenen Runtime besitzt. Dies gilt für die Kombination der Haupt- und Nebenkomponenten der Versionsnummer.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erstellen von Assemblys](create.md)  
 Bietet eine Übersicht über Einfach- und Mehrfachdateiassemblys.  
  
 [Assemblynamen](names.md)  
 Bietet eine Übersicht über die Assemblybenennung.  
  
 [Vorgehensweise: Bestimmen des vollqualifizierten Namens einer Assembly](find-fully-qualified-name.md)  
 Beschreibt, wie der vollqualifizierte Namen einer Assembly bestimmt wird.  
  
 [Ausführen von Intranetanwendungen mit voller Vertrauenswürdigkeit](../../framework/app-domains/running-intranet-applications-in-full-trust.md)  
 Beschreibt, wie Legacysicherheitsrichtlinien für voll vertrauenswürdige Assemblys in einer Intranetfreigabe angegeben werden.  
  
 [Assemblyspeicherort](location.md)  
 Bietet eine Übersicht, wo Assemblys zu finden sind.  
  
 [Vorgehensweise: Erstellen einer Einzeldateiassembly](../../framework/app-domains/build-single-file-assembly.md)  
 Beschreibt das Erstellen einer Assembly mit einer einzigen Datei.  
  
 [Mehrfachdateiassemblys](../../framework/app-domains/multifile-assemblies.md)  
 Beschreibt Gründe für das Erstellen von Assemblys mit mehreren Dateien.  
  
 [Vorgehensweise: Erstellen einer Mehrfachdateiassembly](../../framework/app-domains/build-multifile-assembly.md)  
 Beschreibt das Erstellen einer Assembly mit mehreren Dateien.  
  
 [Festlegen von Assemblyattributen](set-attributes.md)  
 Beschreibt Assemblyattribute und wie diese festgelegt werden.  
  
 [Erstellen und Verwenden von Assemblys mit starkem Namen](create-use-strong-named.md)  
 Beschreibt, wie und warum Sie eine Assembly mit einem starken Namen signieren und enthält Themen zur Vorgehensweise.  
  
 [Verzögertes Signieren einer Assembly](delay-sign.md)  
 Beschreibt, wie eine Assembly verzögert signiert wird.  
  
 [Arbeiten mit Assemblys und dem globalen Assemblycache](../../framework/app-domains/working-with-assemblies-and-the-gac.md)  
 Beschreibt, wie und warum Sie Assemblys zum globalen Assemblycache hinzufügen und enthält Themen zur Vorgehensweise.  
  
 [Vorgehensweise: Anzeigen des Assemblyinhalts](view-contents.md)  
 Beschreibt, wie Sie MSIL Disassembler (Ildasm.exe) zum Anzeigen von Assemblyinhalten verwenden.  
  
 [Typweiterleitung in der Common Language Runtime](type-forwarding.md)  
 Beschreibt, wie die Typweiterleitung zum Verschieben eines Typs in eine andere Assembly verwendet wird, ohne dass vorhandene Anwendungen unterbrochen werden.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Reflection.Assembly>  
 Die .NET Framework-Klasse, die eine Assembly darstellt.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Vorgehensweise: Abrufen von Typ- und Memberinformationen aus einer Assembly](../../framework/reflection-and-codedom/get-type-member-information.md)  
 Beschreibt, wie Typen oder andere Informationen programmgesteuert von einer Assembly abgerufen werden.  
  
 [Assemblys in .NET](index.md)  
 Konzeptuelle Übersicht über Assemblys der Common Language Runtime.  
  
 [Versionsverwaltung für Assemblys](versioning.md)  
 Bietet eine Übersicht zur Bindung von Assemblys und der <xref:System.Reflection.AssemblyVersionAttribute>- und <xref:System.Reflection.AssemblyInformationalVersionAttribute>-Attribute.  
  
 [So sucht Common Language Runtime nach Assemblys](../../framework/deployment/how-the-runtime-locates-assemblies.md)  
 Beschreibt, wie die Runtime ermittelt, welche Assembly zur Erfüllung einer Bindungsanforderung verwendet wird.  
  
 [Reflection (Reflektion)](../../framework/reflection-and-codedom/reflection.md)   
 Beschreibt, wie die **Reflektion**-Klasse verwendet wird, um Informationen zu einer Assembly abzurufen.
