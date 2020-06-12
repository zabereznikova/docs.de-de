---
title: Erweitern von Metadaten mithilfe von Attributen
description: Hier erfahren Sie, wie Sie Metadaten mithilfe von Attributen in .NET erweitern. Attribute sind beschreibende Deklarationen, die Schlüsselworten ähneln und dazu dienen, Programmierelemente wie Typen und Felder zu kommentieren.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- metadata, extending
- attributes [.NET Framework], metadata
- elements [.NET Framework], attributes
- common language runtime, attributes
- annotating programming elements
- keyword-like descriptive declarations
- runtime, attributes
- extending metadata
ms.assetid: 30386922-1e00-4602-9ebf-526b271a8b87
ms.openlocfilehash: c77de970c5550bd896e83854414592d70eb9dc48
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598631"
---
# <a name="extending-metadata-using-attributes"></a>Erweitern von Metadaten mithilfe von Attributen
Die Common Language Runtime (CLR) ermöglicht Ihnen, schlüsselwortähnliche beschreibende Deklarationen (sogenannte Attribute) hinzuzufügen, um Programmierelemente wie Typen, Felder, Methoden und Eigenschaften mit Anmerkungen zu versehen. Beim Kompilieren von Code für die Laufzeit wird dieser in die Microsoft Intermediate Language (MSIL) konvertiert und mit den vom Compiler generierten Metadaten in einer PE-Datei (Portable Executable) abgelegt. Mit Attributen können Sie Metadaten weitere beschreibende Informationen hinzufügen, die mit Reflexionsdiensten zur Laufzeit extrahiert werden können. Der Compiler erstellt Attribute, wenn Sie Instanzen spezieller Klassen deklarieren, die von <xref:System.Attribute?displayProperty=nameWithType> abgeleitet werden.  
  
 In .NET Framework werden Attribute aus unterschiedlichen Gründen eingesetzt und zur Lösung verschiedener Probleme verwendet. Attribute beschreiben das Serialisieren von Daten, legen Eigenschaften zum Erzwingen von Sicherheit fest und beschränken Optimierungen durch den JIT-Compiler (Just-In-Time), sodass auch weiterhin ein einfaches Debuggen des Codes möglich ist. Außerdem können Attribute auch einen Dateinamen oder den Verfasser von Code aufzeichnen oder  während der Entwicklung von Formularen die Sichtbarkeit von Steuerelementen und Membern steuern.  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Anwenden von Attributen](applying-attributes.md)|In diesem Abschnitt wird die Anwendung eines Attributs auf ein Codeelement beschrieben.|  
|[Verfassen von benutzerdefinierten Attributen](writing-custom-attributes.md)|Beschreibt, wie benutzerdefinierte Attributklassen entworfen werden.|  
|[Abrufen von Informationen aus Attributen](retrieving-information-stored-in-attributes.md)|Beschreibt, wie benutzerdefinierte Attribute für Code abgerufen werden, der in den Ausführungskontext geladen wird.|  
|[Metadaten und selbstbeschreibende Komponenten](../metadata-and-self-describing-components.md)|Dieser Abschnitt enthält  eine Übersicht über Metadaten und beschreibt ihre Implementierung in einer .NET Framework-PE-Datei (Portable Executable).|  
|[How to: Load Assemblies into the Reflection-Only Context](../../framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md) (Gewusst wie: Laden von Assemblys in den auf Reflektion beschränkten Kontext)|Erläutert das Abrufen benutzerdefinierter Attributinformationen in den ausschließlich reflektionsbezogenen Kontext.|  
  
## <a name="reference"></a>Referenz  
 <xref:System.Attribute?displayProperty=nameWithType>
