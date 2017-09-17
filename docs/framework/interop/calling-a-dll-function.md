---
title: Aufrufen einer DLL-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b676599513b923ae46d6ec27d7506435d9cbfcd2
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="calling-a-dll-function"></a>Aufrufen einer DLL-Funktion
Obwohl Aufrufe nicht verwalteter DLL-Funktionen nahezu identisch mit anderen Aufrufen von verwaltetem Code sind, bestehen Unterschiede, die DLL-Funktionen zuerst verwirrend erscheinen lassen. Dieser Abschnitt enthält Themen, in denen einige ungewöhnliche aufrufbezogene Probleme beschrieben werden.  
  
 Strukturen, die von Plattforminvokeaufrufen zurückgegeben werden, müssen Datentypen sein, die die gleiche Darstellung in verwaltetem und nicht verwaltetem Code haben. Solche Typen werden *blitfähige Typen* genannt, da keine Konvertierung erforderlich ist (siehe [Blitfähige und nicht blitfähige Typen](../../../docs/framework/interop/blittable-and-non-blittable-types.md)). Um eine Funktion aufzurufen, die über eine nicht blitfähige Struktur als Rückgabetyp verfügt, können Sie einen blitfähigen Hilfstyp mit derselben Größe wie der nicht blitfähige Typ definieren, und nach der Rückgabe der Funktion Daten konvertieren.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übergeben von Strukturen](../../../docs/framework/interop/passing-structures.md)  
 Identifiziert die Probleme der Übergabe von Datenstrukturen mit einem vordefinierten Layout.  
  
 [Rückruffunktionen](../../../docs/framework/interop/callback-functions.md)  
 Enthält grundlegende Informationen über Rückruffunktionen.  
  
 [Vorgehensweise: Implementieren von Rückruffunktionen](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 Beschreibt das Implementieren von Rückruffunktionen in verwaltetem Code.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Verwenden nicht verwalteter DLL-Funktionen](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 Beschreibt das Aufrufen von nicht verwalteten DLL-Funktionen mithilfe von Plattformaufruf.  
  
 [Marshallen von Daten mit Plattformaufruf](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)  
 Beschreibt, wie Sie Methodenparameter deklarieren und Argumente an Funktionen übergeben, die aus nicht verwalteten Bibliotheken exportiert wurden.

