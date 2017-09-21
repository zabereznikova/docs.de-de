---
title: Marshalling von Zeichenfolgen
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
- marshaling, samples
- platform invoke, marshaling data
- data marshaling, strings
- data marshaling, samples
- data marshaling, platform invoke
- marshaling. strings
- marshaling, platform invoke
- sample applications [.NET Framework], marshaling strings
ms.assetid: e21b078b-70fb-4905-be26-c097ab2433ff
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8d8455d4f1b4dbb463176c06d680b2bd0b1ff9d9
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="marshaling-strings"></a>Marshalling von Zeichenfolgen
Der Plattformaufruf kopiert Zeichenfolgenparameter, wobei das .NET Framework-Format (Unicode) bei Bedarf in das nicht verwaltete Format (ANSI) konvertiert wird. Da verwaltete Zeichenfolgen unveränderlich sind, kopieren Plattformaufrufe sie bei Rückgabe der Funktion nicht aus dem nicht verwalteten Speicher in den verwalteten Arbeitsspeicher.  
  
 In der folgende Tabelle werden Marshallingoptionen für Zeichenfolgen aufgelistet. Ihre Verwendung wird beschrieben, und es werden Links zu den entsprechenden .NET Framework-Beispielen bereitgestellt.  
  
|Zeichenfolge|Beschreibung|Beispiel|  
|------------|-----------------|------------|  
|Nach Wert.|Übergibt Zeichenfolgen als In-Parameter.|[MsgBox](../../../docs/framework/interop/msgbox-sample.md)|  
|Als Ergebnis.|Gibt Zeichenfolgen aus nicht verwaltetem Code zurück.|[Zeichenfolgen](http://msdn.microsoft.com/en-us/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|Nach Verweis.|Übergibt Zeichenfolgen als In/Out-Parameter mit <xref:System.Text.StringBuilder>.|[Puffer](http://msdn.microsoft.com/en-us/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5)|  
|In einer Struktur nach Wert.|Zeichenfolgen werden in einer Struktur, die ein In-Parameter ist, übergeben.|[Strukturen](http://msdn.microsoft.com/en-us/96a62265-dcf9-4608-bc0a-1f762ab9f48e)|  
|In einer Struktur nach Verweis **(char\*)**.|Zeichenfolgen werden in einer Struktur, die ein In/Out-Parameter ist, übergeben. Die nicht verwaltete Funktion erwartet einen Zeiger auf einen Zeichenpuffer, und die Größe des Puffers ist ein Element der Struktur.|[Zeichenfolgen](http://msdn.microsoft.com/en-us/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|In einer Struktur nach Verweis **(char[])**.|Zeichenfolgen werden in einer Struktur, die ein In/Out-Parameter ist, übergeben. Die nicht verwaltete Funktion erwartet einen eingebetteten Zeichenpuffer.|[OSInfo](http://msdn.microsoft.com/en-us/69d89067-507b-41fe-859d-30bf3ff29455)|  
|In einer Klasse nach Wert **(char\*)**.|Zeichenfolgen werden in einer Klasse übergeben (eine Klasse ist ein In/Out-Parameter). Die nicht verwaltete Funktion erwartet einen Zeiger auf einen Zeichenpuffer.|[OpenFileDlg](http://msdn.microsoft.com/en-us/b7dea792-cb92-4baf-ac7b-6a24803e6c75)|  
|In einer Klasse nach Wert **(char[])**.|Zeichenfolgen werden in einer Klasse übergeben (eine Klasse ist ein In/Out-Parameter). Die nicht verwaltete Funktion erwartet einen eingebetteten Zeichenpuffer.|[OSInfo](http://msdn.microsoft.com/en-us/69d89067-507b-41fe-859d-30bf3ff29455)|  
|Als Array aus Zeichenfolgen nach Wert.|Erstellt ein Array aus Zeichenfolgen, das als Wert übergeben wird.|[Arrays](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
|Als ein Array von Strukturen, das Zeichenfolgen nach Wert enthält.|Erstellt ein Array von Strukturen, das Zeichenfolgen enthält, und das Array wird nach Wert übergeben.|[Arrays](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a>Siehe auch  
 [Marshaling Data with Platform Invoke (Marshallen von Daten mit Plattformaufruf)](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)   
 [Datentypen für den Plattformaufruf](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [Marshallen von Klassen, Strukturen und Unions](../../../docs/framework/interop/marshaling-classes-structures-and-unions.md)   
 [Marshallen von Typenarrays](http://msdn.microsoft.com/en-us/049b1c1b-228f-4445-88ec-91bc7fd4b1e8)   
 [Verschiedene Marshallingbeispiele](http://msdn.microsoft.com/en-us/a915c948-54e9-4d0f-a525-95a77fd8ed70)

