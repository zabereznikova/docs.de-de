---
title: Marshalling von Zeichenfolgen
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc4f40ab954a3bb31e0b55aad8c00ed2ee63f6c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514893"
---
# <a name="marshaling-strings"></a>Marshalling von Zeichenfolgen
Der Plattformaufruf kopiert Zeichenfolgenparameter, wobei das .NET Framework-Format (Unicode) bei Bedarf in das nicht verwaltete Format (ANSI) konvertiert wird. Da verwaltete Zeichenfolgen unveränderlich sind, kopieren Plattformaufrufe sie bei Rückgabe der Funktion nicht aus dem nicht verwalteten Speicher in den verwalteten Arbeitsspeicher.  
  
 In der folgende Tabelle werden Marshallingoptionen für Zeichenfolgen aufgelistet. Ihre Verwendung wird beschrieben, und es werden Links zu den entsprechenden .NET Framework-Beispielen bereitgestellt.  
  
|Zeichenfolge|Beschreibung|Beispiel|  
|------------|-----------------|------------|  
|Nach Wert.|Übergibt Zeichenfolgen als In-Parameter.|[MsgBox](msgbox-sample.md)|  
|Als Ergebnis.|Gibt Zeichenfolgen aus nicht verwaltetem Code zurück.|[Zeichenfolgen](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))|  
|Nach Verweis.|Übergibt Zeichenfolgen als In/Out-Parameter mit <xref:System.Text.StringBuilder>.|[Puffer](https://msdn.microsoft.com/library/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5(v=vs.100))|  
|In einer Struktur nach Wert.|Zeichenfolgen werden in einer Struktur, die ein In-Parameter ist, übergeben.|[Strukturen](https://msdn.microsoft.com/library/96a62265-dcf9-4608-bc0a-1f762ab9f48e(v=vs.100))|  
|In einer Struktur nach Verweis **(char\*)**.|Zeichenfolgen werden in einer Struktur, die ein In/Out-Parameter ist, übergeben. Die nicht verwaltete Funktion erwartet einen Zeiger auf einen Zeichenpuffer, und die Größe des Puffers ist ein Element der Struktur.|[Zeichenfolgen](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))|  
|In einer Struktur nach Verweis **(char[])**.|Zeichenfolgen werden in einer Struktur, die ein In/Out-Parameter ist, übergeben. Die nicht verwaltete Funktion erwartet einen eingebetteten Zeichenpuffer.|[OSInfo](https://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455(v=vs.100))|  
|In einer Klasse nach Wert **(char\*)**.|Zeichenfolgen werden in einer Klasse übergeben (eine Klasse ist ein In/Out-Parameter). Die nicht verwaltete Funktion erwartet einen Zeiger auf einen Zeichenpuffer.|[OpenFileDlg](https://msdn.microsoft.com/library/b7dea792-cb92-4baf-ac7b-6a24803e6c75(v=vs.100))|  
|In einer Klasse nach Wert **(char[])**.|Zeichenfolgen werden in einer Klasse übergeben (eine Klasse ist ein In/Out-Parameter). Die nicht verwaltete Funktion erwartet einen eingebetteten Zeichenpuffer.|[OSInfo](https://msdn.microsoft.com/library/69d89067-507b-41fe-859d-30bf3ff29455(v=vs.100))|  
|Als Array aus Zeichenfolgen nach Wert.|Erstellt ein Array aus Zeichenfolgen, das als Wert übergeben wird.|[Arrays](marshaling-different-types-of-arrays.md)|  
|Als ein Array von Strukturen, das Zeichenfolgen nach Wert enthält.|Erstellt ein Array von Strukturen, das Zeichenfolgen enthält, und das Array wird nach Wert übergeben.|[Arrays](marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a>Siehe auch
- [Marshallen von Daten mit Plattformaufruf](marshaling-data-with-platform-invoke.md)
- [Datentypen für den Plattformaufruf](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))
- [Marshallen von Klassen, Strukturen und Unions](marshaling-classes-structures-and-unions.md)
- [Marshallen von Typenarrays](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))
- [Verschiedene Marshallingbeispiele](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))
