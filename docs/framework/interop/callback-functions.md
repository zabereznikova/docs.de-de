---
title: "Rückruffunktionen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c4f39160e817ce04c5c15fb8299852a052d36c25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="callback-functions"></a>Rückruffunktionen
Eine Rückruffunktion ist ein Code innerhalb einer verwalteten Anwendung, mit dem eine nicht verwaltete DLL-Funktion eine Aufgabe ausführen kann. Aufrufe einer Rückruffunktion werden indirekt von einer verwalteten Anwendung über eine DLL-Funktion und zurück an die verwaltete Implementierung übergeben. Einige der vielen DLL-Funktionen, die mit dem Plattformaufruf aufgerufen werden, erfordern eine Rückruffunktion in verwaltetem Code zur ordnungsgemäßen Ausführung.  
  
 Um die meisten DLL-Funktionen aus verwaltetem Code aufzurufen, erstellen Sie eine verwaltete Definition der Funktion, und rufen Sie sie dann auf. Der Vorgang ist einfach.  
  
 Die Verwendung einer DLL-Funktion, die eine Rückruffunktion benötigt, erfordert einige zusätzliche Schritte. Zunächst müssen Sie durch einen Blick auf die Dokumentation der Funktion ermitteln, ob die Funktion einen Rückruf erfordert. Als Nächstes müssen Sie die Rückruffunktion in einer verwalteten Anwendung erstellen. Zum Schluss rufen Sie die DLL-Funktion auf, indem Sie als Argument einen Zeiger an die Rückruffunktion übergeben. Diese Schritte werden in der folgenden Abbildung veranschaulicht.  
  
 ![Rückruf für Plattformaufruf](../../../docs/framework/interop/media/pinvokecallback.gif "Pinvokecallback")  
Rückruffunktion und Implementierung  
  
 Rückruffunktionen eignen sich ideal für die Verwendung in Situationen, in denen eine Aufgabe wiederholt ausgeführt wird. Eine andere allgemeine Verwendung ist die Nutzung von Enumerationsfunktionen, z.B. **EnumFontFamilies**, **EnumPrinters** und **EnumWindows** in der Win32-API. Die **EnumWindows**-Funktion durchläuft alle vorhandenen Fenster auf Ihrem Computer und ruft die Rückruffunktion auf, die einen Task für jedes Fenster durchführt. Anweisungen und ein Beispiel finden Sie unter [Vorgehensweise: Implementieren von Rückruffunktionen](../../../docs/framework/interop/how-to-implement-callback-functions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Implementieren von Rückruffunktionen](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 [Calling a DLL Function (Aufrufen einer DLL-Funktion)](../../../docs/framework/interop/calling-a-dll-function.md)
