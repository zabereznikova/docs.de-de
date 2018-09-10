---
title: Ausgeben von dynamischen Methoden und Assemblys
ms.date: 08/30/2017
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a0ed1d02fd40a94d4ae63deea3c09b04bfc9bd8
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44183131"
---
# <a name="emitting-dynamic-methods-and-assemblies"></a>Ausgeben von dynamischen Methoden und Assemblys
In diesem Abschnitt wird ein Satz verwalteter Typen im <xref:System.Reflection.Emit>-Namespace beschrieben, mit denen ein Compiler oder ein Tool zur Laufzeit Metadaten und Microsoft Intermediate Language (MSIL) ausgeben und optional eine übertragbare ausführbare Datei (PE-Datei) auf dem Datenträger generieren kann. Dieser Namespace wird primär von Skript-Engines und Compilern verwendet. Die vom <xref:System.Reflection.Emit>-Namespace bereitgestellte Funktionalität wird in diesem Abschnitt als Reflektionsausgabe bezeichnet.  
  
 Die Reflektionsausgabe bietet die folgenden Funktionen:  
  
-   Sie können mithilfe der <xref:System.Reflection.Emit.DynamicMethod>-Klasse einfache globale Methoden zur Laufzeit definieren und diese mithilfe von Delegaten ausführen.  
  
-   Sie können Assemblys zur Laufzeit definieren und anschließend ausführen und/oder auf dem Datenträger speichern.  
  
-   Sie können Assemblys zur Laufzeit definieren, sie ausführen und dann entladen und der Garbage Collection ermöglichen, die zugehörigen Ressourcen freizugeben.  
  
-   Sie können Module in neuen Assemblys zur Laufzeit definieren und anschließend ausführen und/oder auf dem Datenträger speichern.  
  
-   Sie können Typen in Modulen zur Laufzeit definieren, Instanzen dieser Typen erstellen und deren Methoden aufrufen.  
  
-   Sie können symbolische Informationen für definierte Module angeben, die von Tools wie Debuggern und Codeprofilern verwendet werden können.  
  
 Neben den verwalteten Typen im <xref:System.Reflection.Emit>-Namespace sind nicht verwaltete Metadatenschnittstellen verfügbar, die in der Referenzdokumentation zu [Metadatenschnittstellen](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) beschrieben werden. Die verwaltete Reflektionsausgabe bietet eine bessere semantische Fehlerüberprüfung und einen höheren Abstraktionsgrad für Metadaten als die nicht verwalteten Metadatenschnittstellen.  
  
 In der Common Language Infrastructure(CLI)-Dokumentation, insbesondere in den Themen "Partition II: Metadata Definition and Semantics" und "Partition III: CIL Instruction Set" finden Sie weitere hilfreiche Informationen zur Verwendung von Metadaten und MSIL. Die Dokumentation ist online auf [MSDN](https://go.microsoft.com/fwlink/?LinkID=65555) und der [Ecma-Website](https://go.microsoft.com/fwlink/?LinkId=116487) verfügbar.  
  
## <a name="in-this-section"></a>In diesem Abschnitt
  
[Sicherheitsaspekte bei der Reflektionsausgabe](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)  
Beschreibt Sicherheitsaspekte im Zusammenhang mit dem Erstellen dynamischer Assemblys mithilfe der Reflektionsausgabe.  

[Vorgehensweise: Definieren und Ausführen von dynamischen Methoden](how-to-define-and-execute-dynamic-methods.md)   
Zeigt, wie eine einfache dynamische Methode sowie eine dynamische Methode, die an eine Instanz einer Klasse gebunden ist, ausgeführt werden.

[Vorgehensweise: Definieren eines generischen Typs mit Reflektionsausgabe](how-to-define-a-generic-type-with-reflection-emit.md)   
Zeigt, wie ein einfacher generischer Typ mit zwei Typparametern erstellt wird, wie Klasseneinschränkungen, Schnittstellen und bestimmte Einschränkungen für Typparameter angewandt werden und wie Member erstellt werden, die die Typparameter der Klasse als Parametertypen und Rückgabetypen verwenden.

[Vorgehensweise: Definieren einer generischen Methode mit Reflektionsausgabe](how-to-define-a-generic-method-with-reflection-emit.md)   
Zeigt, wie einfache generische Methoden erstellt, ausgegeben und aufgerufen werden.

[Entladbare Assemblys für die dynamische Typgenerierung](collectible-assemblies.md)   
Führt in das Thema „entladbare Assemblys“ ein. Dabei handelt es sich um dynamische Assemblys, die entladen werden können, ohne gleichzeitig auch die Anwendungsdomäne zu entladen, in der sie erstellt wurden.
  
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
 [Reflexion](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Erläutert das Durchsuchen von Metadaten und verwaltetem Code.  
  
 [Assemblys in der Common Language Runtime (CLR)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Bietet eine Übersicht über Assemblys in .NET-Implementierungen.
