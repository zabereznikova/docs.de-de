---
title: Debuggen von globalen statischen Funktionen
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework debugging]
- debugging global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], debugging
ms.assetid: efc64414-77c3-48d0-881a-8594ed416aad
ms.openlocfilehash: 04906322e311b580abddeca7744cf3e75d471e05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722985"
---
# <a name="debugging-global-static-functions"></a>Debuggen von globalen statischen Funktionen

In diesem Abschnitt werden die nicht verwalteten globalen statischen Funktionen beschrieben, die die Debug-API verwendet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [_EFN_GetManagedExcepStack-Funktion](efn-getmanagedexcepstack-function.md)  
 Gibt bei Angabe der Adresse eines verwalteten Ausnahmeobjekts eine Zeichenfolgenversion der enthaltenen Stapelüberwachung zurück.  
  
 [_EFN_GetManagedObjectFieldInfo-Funktion](efn-getmanagedobjectfieldinfo-function.md)  
 Ruft den Offset vom Beginn eines Objekts zu einem Feld sowie den Wert des Felds mit dem bereitgestellten Objektzeiger und Feldnamen ab.  
  
 [_EFN_GetManagedObjectName-Funktion](efn-getmanagedobjectname-function.md)  
 Ruft den Namen eines Typs mit dem bereitgestellten verwalteten Objektzeiger ab.  
  
 [_EFN_StackTrace-Funktion](efn-stacktrace-function.md)  
 Stellt eine Textdarstellung einer verwalteten Stapelüberwachung und ein Array von `CONTEXT`-Datensätzen bereit, einen Datensatz für jeden Übergang zwischen nicht verwaltetem und verwaltetem Code.  
  
 [CLRDataCreateInstance-Funktion](clrdatacreateinstance-function.md)  
 Wird von den Datenzugriffsdiensten der Common Language Runtime (CLR) aufgerufen, um das angegebene Schnittstellenobjekt für den angegebenen Zielprozess zu erstellen.  
  
 [PFN_CLRDataCreateInstance-Funktionszeiger](pfn-clrdatacreateinstance-function-pointer.md)  
 Verweist auf eine Funktion, die von den Datenzugriffsdiensten der Common Language Runtime (CLR) aufgerufen wird, um das angegebene Schnittstellenobjekt für den angegebenen Zielprozess zu erstellen.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Debuggen von Co-Klassen](debugging-coclasses.md)  
  
 [Debugschnittstellen](debugging-interfaces.md)  
  
 [Debugenumerationen](debugging-enumerations.md)  
  
 [Debuggen von Strukturen](debugging-structures.md)
