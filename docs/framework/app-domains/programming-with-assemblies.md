---
title: Programmieren mit Assemblys
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 368021062a3ad49d2c63f92797c59b8c0f1cddfc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="programming-with-assemblies"></a>Programmieren mit Assemblys
Assemblys sind die Bausteine von .NET Framework; sie bilden das Fundament für Bereitstellung, Versionskontrolle, Wiederverwendung, Gültigkeitsbereiche für die Aktivierung und Sicherheitsberechtigungen. Eine Assembly stellt der Common Language Runtime die Informationen zur Verfügung, die sie zum Erkennen der Typimplementierungen benötigt. Sie ist eine Auflistung von Typen und Ressourcen, die so erstellt wurden, dass sie zusammenarbeiten und eine logische funktionelle Einheit bilden. Für die Common Language Runtime sind Typen nur im Kontext einer Assembly vorhanden.  
  
 In diesem Abschnitt wird beschrieben, wie Module, Assembys aus Modulen und ein Schlüsselpaar erstellt werden, wie eine Assembly mit einem starken Namen signiert wird und wie eine Assembly im globalen Assemblycache installiert wird. Dieser Abschnitt beschreibt zusätzlich, wie Sie [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) verwenden, um Informationen aus dem Assemblymanifest anzuzeigen.  
  
> [!NOTE]
>  Ab der .NET Framework-Version 2.0 lädt die Runtime keine Assembly, die mit einer Version von .NET Framework kompiliert wurde, die eine höhere Versionsnummer als die aktuell geladenen Runtime besitzt. Dies gilt für die Kombination der Haupt- und Nebenkomponenten der Versionsnummer.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md)  
 Bietet eine Übersicht über Einfach- und Mehrfachdateiassemblys.  
  
 [Assemblynamen](../../../docs/framework/app-domains/assembly-names.md)  
 Bietet eine Übersicht über die Assemblybenennung.  
  
 [Gewusst wie: Bestimmen des vollqualifizierten Namens einer Assembly](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 Beschreibt, wie der vollqualifizierte Namen einer Assembly bestimmt wird.  
  
 [Ausführen von Intranetanwendungen mit voller Vertrauenswürdigkeit](../../../docs/framework/app-domains/running-intranet-applications-in-full-trust.md)  
 Beschreibt, wie Legacysicherheitsrichtlinien für voll vertrauenswürdige Assemblys in einer Intranetfreigabe angegeben werden.  
  
 [Assemblyspeicherort](../../../docs/framework/app-domains/assembly-location.md)  
 Bietet eine Übersicht, wo Assemblys zu finden sind.  
  
 [Gewusst wie: Erstellen einer Einzeldateiassembly](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 Beschreibt das Erstellen einer Assembly mit einer einzigen Datei.  
  
 [Mehrfachdateiassemblys](../../../docs/framework/app-domains/multifile-assemblies.md)  
 Beschreibt Gründe für das Erstellen von Assemblys mit mehreren Dateien.  
  
 [Gewusst wie: Erstellen einer Mehrfachdateiassembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 Beschreibt das Erstellen einer Assembly mit mehreren Dateien.  
  
 [Festlegen von Assemblyattributen](../../../docs/framework/app-domains/set-assembly-attributes.md)  
 Beschreibt Assemblyattribute und wie diese festgelegt werden.  
  
 [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 Beschreibt, wie und warum Sie eine Assembly mit einem starken Namen signieren und enthält Themen zur Vorgehensweise.  
  
 [Verzögertes Signieren einer Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 Beschreibt, wie eine Assembly verzögert signiert wird.  
  
 [Arbeiten mit Assemblys und dem globalen Assemblychache](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 Beschreibt, wie und warum Sie Assemblys zum globalen Assemblycache hinzufügen und enthält Themen zur Vorgehensweise.  
  
 [Gewusst wie: Anzeigen des Assemblyinhalts](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 Beschreibt, wie Sie MSIL Disassembler (Ildasm.exe) zum Anzeigen von Assemblyinhalten verwenden.  
  
 [Typweiterleitung in der Common Language Runtime](../../../docs/framework/app-domains/type-forwarding-in-the-common-language-runtime.md)  
 Beschreibt, wie die Typweiterleitung zum Verschieben eines Typs in eine andere Assembly verwendet wird, ohne dass vorhandene Anwendungen unterbrochen werden.  
  
## <a name="reference"></a>Verweis  
 <xref:System.Reflection.Assembly>  
 Die .NET Framework-Klasse, die eine Assembly darstellt.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Gewusst wie: Abrufen von Typ- und Memberinformationen aus einer Assembly](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 Beschreibt, wie Typen oder andere Informationen programmgesteuert von einer Assembly abgerufen werden.  
  
 [Assemblys in der Common Language Runtime (CLR)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Konzeptuelle Übersicht über Assemblys der Common Language Runtime.  
  
 [Assemblyversionen](../../../docs/framework/app-domains/assembly-versioning.md)  
 Bietet eine Übersicht zur Bindung von Assemblys und der <xref:System.Reflection.AssemblyVersionAttribute>- und <xref:System.Reflection.AssemblyInformationalVersionAttribute>-Attribute.  
  
 [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 Beschreibt, wie die Runtime ermittelt, welche Assembly zur Erfüllung einer Bindungsanforderung verwendet wird.  
  
 [Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Beschreibt, wie die **Reflektion**-Klasse verwendet wird, um Informationen zu einer Assembly abzurufen.
