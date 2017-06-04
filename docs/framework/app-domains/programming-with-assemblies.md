---
title: "Programmieren mit Assemblys | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Assemblys [.NET Framework], Programmieren"
  - "Programmieren von Assemblys"
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Programmieren mit Assemblys
Assemblys sind die Grundbausteine von .NET Framework. Sie bilden die Basiseinheit für Bereitstellung, Versionskontrolle, Wiederverwendung, Aktivierungs\-Scoping und Sicherheitsberechtigungen.  Eine Assembly stellt der Common Language Runtime die Informationen zur Verfügung, die sie zum Erkennen der Typimplementierungen benötigt.  Sie stellt eine Auflistung von Typen und Ressourcen dar, die so erstellt wurden, dass sie zusammenarbeiten und eine logische Funktionseinheit bilden.  Für die Common Language Runtime sind Typen nur im Kontext einer Assembly vorhanden.  
  
 In diesem Abschnitt werden folgende Vorgänge beschrieben: das Erstellen von Modulen, das Erstellen von Assemblys aus Modulen, das Erstellen eines Schlüsselpaars, das Signieren einer Assembly mit einem starken Namen und das Installieren einer Assembly im globalen Assemblycache.  Außerdem erfahren Sie in diesem Abschnitt, wie mithilfe des [MSIL Disassembler\-Tools \(Ildasm.exe\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) Assemblymanifestinformationen angezeigt werden.  
  
> [!NOTE]
>  Ab .NET Framework, Version 2.0, lädt die Laufzeit keine Assemblys mehr, die mit einer Version von .NET Framework kompiliert wurden, deren Versionsnummer höher ist als die der aktuell geladenen Laufzeit.  Dies gilt für die Kombination aus den Haupt\- und Nebenkomponenten der Versionsnummer.  
  
## In diesem Abschnitt  
 [Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md)  
 Bietet eine Übersicht über Einfach\- und Mehrfachdateiassemblys.  
  
 [Assemblynamen](../../../docs/framework/app-domains/assembly-names.md)  
 Bietet eine Übersicht über die Namensvergabe für Assemblys.  
  
 [Gewusst wie: Bestimmen des vollqualifizierten Namens einer Assembly](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 Beschreibt, wie der vollqualifizierte Name einer Assembly bestimmt wird.  
  
 [Ausführen von Intranetanwendungen mit voller Vertrauenswürdigkeit](../../../docs/framework/app-domains/running-intranet-applications-in-full-trust.md)  
 Beschreibt, wie eine Legacysicherheitsrichtlinie für voll vertrauenswürdige Assemblys in einer Intranetfreigabe angegeben wird.  
  
 [Assemblyspeicherort](../../../docs/framework/app-domains/assembly-location.md)  
 Bietet eine Übersicht über das Suchen nach Assemblys.  
  
 [Gewusst wie: Erstellen einer Einzeldateiassembly](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 Beschreibt das Erstellen einer Einfachdateiassembly.  
  
 [Mehrfachdateiassemblys](../../../docs/framework/app-domains/multifile-assemblies.md)  
 Beschreibt die Gründe für ein Erstellen von Mehrfachdateiassemblys.  
  
 [Gewusst wie: Erstellen einer Mehrfachdateiassembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 Beschreibt das Erstellen einer Mehrfachdateiassembly.  
  
 [Festlegen von Assemblyattributen](../../../docs/framework/app-domains/set-assembly-attributes.md)  
 Beschreibt Assemblyattribute und wie diese festgelegt werden.  
  
 [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 Beschreibt, wie und warum Assemblys mit starkem Namen signiert werden, und enthält Gewusst\-wie\-Themen.  
  
 [Verzögertes Signieren einer Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 Beschreibt das verzögerte Signieren einer Assembly.  
  
 [Arbeiten mit Assemblys und dem globalen Assemblychache](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 Beschreibt, wie und warum Assemblys dem globalen Assemblycache hinzugefügt werden, und enthält Gewusst\-wie\-Themen.  
  
 [Gewusst wie: Ansichtsassemblyinhalt](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 Beschreibt das Verwenden des MSIL Disassembler\-Tools \(Ildasm.exe\) zur Anzeige von Assemblyinhalten.  
  
 [Typweiterleitung in der Common Language Runtime](../../../docs/framework/app-domains/type-forwarding-in-the-common-language-runtime.md)  
 Beschreibt das Verwenden einer Typweiterleitung zum Verschieben eines Typs in eine andere Assembly, ohne die Konsistenz von Code vorhandener Anwendungen zu zerstören.  
  
## Referenz  
 <xref:System.Reflection.Assembly>  
 Die .NET Framework\-Klasse, die eine Assembly darstellt.  
  
## Verwandte Abschnitte  
 [Gewusst wie: Abrufen von Typ\- und Memberinformationen aus einer Assembly](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 Beschreibt das programmgesteuerte Abrufen von Typ\- und anderen Informationen aus einer Assembly.  
  
 [Assemblys in der Common Language Runtime \(CLR\)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Bietet eine konzeptionelle Übersicht über Common Language Runtime\-Assemblys.  
  
 [Assemblyversionen](../../../docs/framework/app-domains/assembly-versioning.md)  
 Bietet eine Übersicht über die Assemblybindung sowie über das <xref:System.Reflection.AssemblyVersionAttribute>\-Attribut und <xref:System.Reflection.AssemblyInformationalVersionAttribute>\-Attribut.  
  
 [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 Beschreibt, wie die Common Language Runtime ermittelt, welche Assembly zur Erfüllung einer Bindungsanforderung verwendet wird.  
  
 [Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Beschreibt das Verwenden der **Reflection**\-Klasse, um Informationen zu einer Assembly zu erhalten.