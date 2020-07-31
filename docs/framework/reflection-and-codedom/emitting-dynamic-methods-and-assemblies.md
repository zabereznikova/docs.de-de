---
title: Ausgeben von dynamischen Methoden und Assemblys
description: Hier erfahren Sie, wie Sie dynamische Methoden und Assemblys mithilfe des Namespace „System.Reflection.Emit“ ausgeben. So können ein Compiler oder ein Tool Metadaten und MSIL-Code zur Laufzeit ausgeben.
ms.date: 08/30/2017
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.openlocfilehash: 76d2a83943d9df06cc66cf86c6869f18fac2a12c
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475046"
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
  
In der Common Language Infrastructure(CLI)-Dokumentation, insbesondere in den Themen "Partition II: Metadatendefinition und Semantik) und „Partition III: CIL Instruction Set“ (Partition III: CIL-Anweisungen). Die Dokumentation ist online auf der [Ecma-Website](https://www.ecma-international.org/publications/standards/Ecma-335.htm) verfügbar.  
  
## <a name="in-this-section"></a>In diesem Abschnitt
  
[Sicherheitsaspekte bei der Reflektionsausgabe](security-issues-in-reflection-emit.md)  
Beschreibt Sicherheitsaspekte im Zusammenhang mit dem Erstellen dynamischer Assemblys mithilfe der Reflektionsausgabe.  

[How to: Definieren und Ausführen von dynamischen Methoden:](how-to-define-and-execute-dynamic-methods.md) Zeigt, wie eine einfache dynamische Methode sowie eine dynamische Methode, die an eine Instanz einer Klasse gebunden ist, ausgeführt werden

[How to: Definieren eines generischen Typs mit Reflexionsausgabe:](how-to-define-a-generic-type-with-reflection-emit.md) Zeigt, wie ein einfacher generischer Typ mit zwei Typparametern erstellt wird, wie Klasseneinschränkungen, Schnittstelleneinschränkungen und bestimmte Einschränkungen für Typparameter angewandt werden und wie Member erstellt werden, die die Typparameter der Klasse als Parameter- und Rückgabetypen verwenden.

[How to: Definieren einer generischen Methode mit Reflexionsausgabe:](how-to-define-a-generic-method-with-reflection-emit.md) Zeigt, wie eine einfache generische Methode erstellt, ausgegeben und aufgerufen wird

[Entladbare Assemblys für die dynamische Typgenerierung:](collectible-assemblies.md) Führt entladbare Assemblys ein. Dabei handelt es sich um dynamische Assemblys, die entladen werden können, ohne gleichzeitig auch die Anwendungsdomäne zu entladen, in der sie erstellt wurden.
  
## <a name="reference"></a>Referenz  

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
