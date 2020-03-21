---
title: Ausgeben von dynamischen Methoden und Assemblys
ms.date: 08/30/2017
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.openlocfilehash: fda5a20eb7798086ec10415889454b4a8beba5f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180526"
---
# <a name="emitting-dynamic-methods-and-assemblies"></a>Ausgeben von dynamischen Methoden und Assemblys

In diesem Abschnitt wird ein Satz verwalteter Typen im <xref:System.Reflection.Emit>-Namespace beschrieben, mit denen ein Compiler oder ein Tool zur Laufzeit Metadaten und Microsoft Intermediate Language (MSIL) ausgeben und optional eine übertragbare ausführbare Datei (PE-Datei) auf dem Datenträger generieren kann. Dieser Namespace wird primär von Skript-Engines und Compilern verwendet. Die vom <xref:System.Reflection.Emit>-Namespace bereitgestellte Funktionalität wird in diesem Abschnitt als Reflektionsausgabe bezeichnet.  
  
Die Reflektionsausgabe bietet die folgenden Funktionen:  
  
- Sie können mithilfe der <xref:System.Reflection.Emit.DynamicMethod>-Klasse einfache globale Methoden zur Laufzeit definieren und diese mithilfe von Delegaten ausführen.  
  
- Sie können Assemblys zur Laufzeit definieren und anschließend ausführen und/oder auf dem Datenträger speichern.  
  
- Sie können Assemblys zur Laufzeit definieren, sie ausführen und dann entladen und der Garbage Collection ermöglichen, die zugehörigen Ressourcen freizugeben.  
  
- Sie können Module in neuen Assemblys zur Laufzeit definieren und anschließend ausführen und/oder auf dem Datenträger speichern.  
  
- Sie können Typen in Modulen zur Laufzeit definieren, Instanzen dieser Typen erstellen und deren Methoden aufrufen.  
  
- Sie können symbolische Informationen für definierte Module angeben, die von Tools wie Debuggern und Codeprofilern verwendet werden können.  
  
Neben den verwalteten Typen im <xref:System.Reflection.Emit>-Namespace sind nicht verwaltete Metadatenschnittstellen verfügbar, die in der Referenzdokumentation zu [Metadatenschnittstellen](../unmanaged-api/metadata/metadata-interfaces.md) beschrieben werden. Die verwaltete Reflektionsausgabe bietet eine bessere semantische Fehlerüberprüfung und einen höheren Abstraktionsgrad für Metadaten als die nicht verwalteten Metadatenschnittstellen.  
  
In der Common Language Infrastructure(CLI)-Dokumentation, insbesondere in den Themen "Partition II: Metadata Definition and Semantics" und "Partition III: CIL Instruction Set" finden Sie weitere hilfreiche Informationen zur Verwendung von Metadaten und MSIL. Die Dokumentation ist online auf der [Ecma-Website](https://www.ecma-international.org/publications/standards/Ecma-335.htm)verfügbar.  
  
## <a name="in-this-section"></a>In diesem Abschnitt
  
[Sicherheitsprobleme in der Reflexion emittieren](security-issues-in-reflection-emit.md)  
Beschreibt Sicherheitsaspekte im Zusammenhang mit dem Erstellen dynamischer Assemblys mithilfe der Reflektionsausgabe.  

[Gewusst wie: Definieren und Ausführen dynamischer Methoden](how-to-define-and-execute-dynamic-methods.md) Zeigt, wie eine einfache dynamische Methode und eine dynamische Methode ausgeführt werden, die an eine Instanz einer Klasse gebunden ist.

[Gewusst wie: Definieren eines generischen Typs mit Reflexionsee](how-to-define-a-generic-type-with-reflection-emit.md) Zeigt, wie sie einen einfachen generischen Typ mit zwei Typparametern erstellen, Klassen-, Schnittstellen- und Sondereinschränkungen auf die Typparameter anwenden und wie Member erstellt werden, die die Typparameter der Klasse als Parametertypen und Rückgabetypen verwenden.

[Gewusst wie: Definieren einer generischen Methode mit Reflexionsee](how-to-define-a-generic-method-with-reflection-emit.md) Zeigt, wie eine einfache generische Methode erstellt, ausgesendet und aufgerufen wird.

[Sammelbaugruppen für die dynamische Typgenerierung](collectible-assemblies.md) Führt Sammelassemblys ein, bei denen es sich um dynamische Assemblys handelt, die entladen werden können, ohne die Anwendungsdomäne zu entladen, in der sie erstellt wurden.
  
## <a name="reference"></a>Verweis  

<xref:System.Reflection.Emit.OpCodes>  
Hier werden die MSIL-Anweisungcodes zum Erstellen von Methodentexten katalogisiert.  
  
<xref:System.Reflection.Emit>  
Hier werden verwaltete Klassen aufgeführt, die zum Ausgeben von dynamischen Methoden, Assemblys und Typen verwendet werden.  
  
<xref:System.Type>  
Hier wird die <xref:System.Type>-Klasse beschrieben, die Typen in der verwalteten Reflektion und Reflektionsausgabe darstellt. Diese Klasse ist das wichtigste Element bei der Verwendung dieser Technologien.  
  
<xref:System.Reflection>  
Hier werden verwaltete Klassen aufgeführt, die zum Durchsuchen von Metadaten und verwaltetem Code verwendet werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

[Reflexion](reflection.md)  
Erläutert das Durchsuchen von Metadaten und verwaltetem Code.  
  
[Assemblys in .NET](../../standard/assembly/index.md)  
Bietet eine Übersicht über Assemblys in .NET-Implementierungen.
