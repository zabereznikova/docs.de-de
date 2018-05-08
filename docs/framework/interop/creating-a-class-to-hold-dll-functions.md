---
title: Erstellen einer Klasse zum Halten von DLL-Funktionen
ms.date: 03/30/2017
helpviewer_keywords:
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke, creating class for functions
- DLL functions
ms.assetid: e08e4c34-0223-45f7-aa55-a3d8dd979b0f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09088d1ac0a8312ee5832a5f3bc0547e6654de93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-class-to-hold-dll-functions"></a>Erstellen einer Klasse zum Halten von DLL-Funktionen
Das Umschließen einer häufig verwendeten DLL-Funktion in einer verwalteten Klasse ist als effektiver Ansatz zu verstehen, Plattformfunktionen zu kapseln. Obwohl es nicht in jedem Fall erforderlich ist, können Sie mithilfe von Klassenwrappern DLL-Funktionen mit weniger Aufwand und geringerer Fehleranfälligkeit definieren. Wenn Sie in Visual Basic oder C# programmieren, müssen Sie die DLL-Funktionen innerhalb einer Klasse oder eines Visual Basic-Moduls deklarieren.  
  
 Innerhalb einer Klasse definieren Sie eine statische Methode für jede DLL-Funktion, die Sie aufrufen möchten. Die Definition kann zusätzliche Informationen wie den Zeichensatz oder die Aufrufkonvention, die bei der Übergabe von Methodenargumenten verwendet wird, enthalten; werden diese Informationen weggelassen, werden die Standardeinstellungen verwendet. Eine vollständige Liste der Deklarationsoptionen und deren Standardeinstellungen finden Sie unter [Erstellen von Prototypen in verwaltetem Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).  
  
 Sobald umschlossen ist, können Sie die Methoden für die Klasse aufrufen, wie Sie statische Methoden für jede andere Klasse aufrufen. Der Plattformaufruf behandelt automatisch die zugrunde liegenden exportierten Funktionen.  
  
 Beim Entwurf einer verwalteten Klasse für Plattformaufruf, beachten Sie die Beziehungen zwischen Klassen und DLL-Funktionen. Sie haben unter anderem folgende Möglichkeiten:  
  
-   Deklarieren von DLL-Funktionen innerhalb einer vorhandenen Klasse.  
  
-   Erstellen Sie eine einzelne Klasse für jede DLL-Funktion, indem Funktionen isoliert und leicht auffindbar bleiben.  
  
-   Erstellen Sie eine Klasse für eine Gruppe von verwandten DLL-Funktionen, um logische Gruppierungen zu bilden und den Verwaltungsaufwand zu reduzieren.  
  
 Sie können die Klasse und ihre Methoden beliebig benennen. Beispiele für die Vorgehensweise beim Erstellen von .NET-basierten Deklarationen, die mit dem Plattformaufruf verwendet werden können, finden Sie unter [Marshaling Data with Platform Invoke (Marshallen von Daten mit Plattformaufruf)](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden nicht verwalteter DLL-Funktionen](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 [Identifizieren von Funktionen in DLLs](../../../docs/framework/interop/identifying-functions-in-dlls.md)  
 [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [Calling a DLL Function (Aufrufen einer DLL-Funktion)](../../../docs/framework/interop/calling-a-dll-function.md)
