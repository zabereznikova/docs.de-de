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
ms.openlocfilehash: 88b6342038f99bf06fa2986c43f422e63cffd31e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124382"
---
# <a name="marshaling-strings"></a>Marshalling von Zeichenfolgen
Der Plattformaufruf kopiert Zeichenfolgenparameter, wobei das .NET Framework-Format (Unicode) bei Bedarf in das nicht verwaltete Format (ANSI) konvertiert wird. Da verwaltete Zeichenfolgen unveränderlich sind, kopieren Plattformaufrufe sie bei Rückgabe der Funktion nicht aus dem nicht verwalteten Speicher in den verwalteten Arbeitsspeicher.  
  
 In der folgende Tabelle werden Marshallingoptionen für Zeichenfolgen aufgelistet. Ihre Verwendung wird beschrieben, und es werden Links zu den entsprechenden .NET Framework-Beispielen bereitgestellt.  
  
|Zeichenfolge|Beschreibung|Beispiel|  
|------------|-----------------|------------|  
|Nach Wert.|Übergibt Zeichenfolgen als In-Parameter.|[MsgBox](msgbox-sample.md)|  
|Als Ergebnis.|Gibt Zeichenfolgen aus nicht verwaltetem Code zurück.|[Zeichenfolgen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e765dyyy(v=vs.100))|  
|Nach Verweis.|Übergibt Zeichenfolgen als In/Out-Parameter mit <xref:System.Text.StringBuilder>.|[Puffer](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x3txb6xc(v=vs.100))|  
|In einer Struktur nach Wert.|Zeichenfolgen werden in einer Struktur, die ein In-Parameter ist, übergeben.|[Strukturen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100))|  
|In einer Struktur nach Verweis **(char\*)** .|Zeichenfolgen werden in einer Struktur, die ein In/Out-Parameter ist, übergeben. Die nicht verwaltete Funktion erwartet einen Zeiger auf einen Zeichenpuffer, und die Größe des Puffers ist ein Element der Struktur.|[Zeichenfolgen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e765dyyy(v=vs.100))|  
|In einer Struktur nach Verweis **(char[])** .|Zeichenfolgen werden in einer Struktur, die ein In/Out-Parameter ist, übergeben. Die nicht verwaltete Funktion erwartet einen eingebetteten Zeichenpuffer.|[OSInfo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))|  
|In einer Klasse nach Wert **(char\*)** .|Zeichenfolgen werden in einer Klasse übergeben (eine Klasse ist ein In/Out-Parameter). Die nicht verwaltete Funktion erwartet einen Zeiger auf einen Zeichenpuffer.|[OpenFileDlg](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w5tyztk9(v=vs.100))|  
|In einer Klasse nach Wert **(char[])** .|Zeichenfolgen werden in einer Klasse übergeben (eine Klasse ist ein In/Out-Parameter). Die nicht verwaltete Funktion erwartet einen eingebetteten Zeichenpuffer.|[OSInfo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))|  
|Als Array aus Zeichenfolgen nach Wert.|Erstellt ein Array aus Zeichenfolgen, das als Wert übergeben wird.|[Arrays](marshaling-different-types-of-arrays.md)|  
|Als ein Array von Strukturen, das Zeichenfolgen nach Wert enthält.|Erstellt ein Array von Strukturen, das Zeichenfolgen enthält, und das Array wird nach Wert übergeben.|[Arrays](marshaling-different-types-of-arrays.md)|  
  
## <a name="see-also"></a>Siehe auch

- [Standardmäßiges Marshalling für Zeichenfolgen](default-marshaling-for-strings.md)
- [Marshallen von Daten mit Plattformaufruf](marshaling-data-with-platform-invoke.md)
- [Marshallen von Klassen, Strukturen und Unions](marshaling-classes-structures-and-unions.md)
- [Maushallen verschiedener Typen von Arrays](marshaling-different-types-of-arrays.md)
- [Verschiedene Marshallingbeispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ss9sb93t(v=vs.100))
