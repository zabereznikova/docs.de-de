---
title: Marshalling von Typen – .NET
description: Erfahren Sie, wie .NET Ihre Strukturen in eine native Darstellung marshallt.
ms.date: 01/18/2019
ms.openlocfilehash: 91b8f3d6cb53fd7a0adea7ea9669e7459e81445f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706265"
---
# <a name="type-marshaling"></a>Marshalling von Typen

Das **Marshallen** bezeichnet den Vorgang zum Umwandeln von Typen, wenn diese zwischen verwaltetem und nativem Code wechseln müssen.

Das Marshallen ist erforderlich, weil sich die Typen in verwaltetem und nicht verwaltetem Code unterscheiden. In verwaltetem Code haben Sie z. b. eine `String`, während Zeichen folgen in der nicht verwalteten Welt Unicode ("Wide"), nicht-Unicode, mit NULL endend, ASCII usw. sein können. Standardmäßig versucht das P/aufrufen-Subsystem, das richtige zu tun, basierend auf dem Standardverhalten, das in diesem Artikel beschrieben wird. In Situationen, in denen Sie zusätzliche Kontrolle benötigen, können Sie das [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute)-Attribut verwenden, um anzugeben, welcher Typ auf der nicht verwalteten Seite erwartet wird. Wenn Sie beispielsweise die Zeichenfolge als nicht mit NULL endende ANSI-Zeichenfolge senden möchten, können Sie dies folgendermaßen erreichen:

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

## <a name="default-rules-for-marshaling-common-types"></a>Standardregeln für das Marshallen von häufig verwendeten Typen

Allgemein versucht die Runtime, beim Marshallen das „Richtige“ zu tun, damit Sie möglichst wenig Arbeitsaufwand haben. Die folgenden Tabellen beschreiben das standardmäßige Marshallen der einzelnen Typen bei Verwendung in einem Parameter oder Feld. Die Integer- und Zeichentypen mit fester Breite von C99/C++11 werden verwendet, um sicherzustellen, dass die folgende Tabelle für alle Plattformen richtig ist. Sie können jeden nativen Typen verwenden, der die gleichen Anforderungen an Ausrichtung und Größe aufweist wie diese Typen.

Die erste Tabelle beschreibt die Zuordnungen für verschiedene Typen, für die das Marshallen für P/Invoke und Feldmarshalling gleich ist.

| .NET-Typ | Nativer Typ  |
|-----------|-------------------------|
| `byte`    | `uint8_t`               |
| `sbyte`   | `int8_t`                |
| `short`   | `int16_t`               |
| `ushort`  | `uint16_t`              |
| `int`     | `int32_t`               |
| `uint`    | `uint32_t`              |
| `long`    | `int64_t`               |
| `ulong`   | `uint64_t`              |
| `char`    | Entweder `char` oder `char16_t`, je nach `CharSet` von P/Invoke oder der Struktur. Informationen dazu finden Sie in der [Dokumentation zum Zeichensatz](charset.md). |
| `string`  | Entweder `char*` oder `char16_t*`, je nach `CharSet` von P/Invoke oder der Struktur. Informationen dazu finden Sie in der [Dokumentation zum Zeichensatz](charset.md). |
| `System.IntPtr` | `intptr_t`        |
| `System.UIntPtr` | `uintptr_t`      |
| .NET-Zeigertypen (z.B. `void*`)  | `void*` |
| Von `System.Runtime.InteropServices.SafeHandle` abgeleiteter Typ | `void*` |
| Von `System.Runtime.InteropServices.CriticalHandle` abgeleiteter Typ | `void*`          |
| `bool`    | Win32-`BOOL`-Typ       |
| `decimal` | COM-`DECIMAL`-Struktur |
| .NET-Delegat | Nativer Funktionszeiger |
| `System.DateTime` | Win32-`DATE`-Typ |
| `System.Guid` | Win32-`GUID`-Typ |

Einige Marshallingkategorien weisen unterschiedliche Standardwerte auf, wenn Sie das Marshalling als Parameter oder Struktur durchführen.

| .NET-Typ | Nativer Typ (Parameter) | Nativer Typ (Feld) |
|-----------|-------------------------|---------------------|
| .NET-Array | Ein Zeiger auf den Anfang eines Arrays aus nativen Darstellungen der Arrayelemente | Ohne `[MarshalAs]`-Attribut nicht zulässig|
| Eine Klasse mit einem `LayoutKind`-Wert vom Typ `Sequential` oder `Explicit` | Ein Zeiger auf die native Darstellung der Klasse | Die native Darstellung der Klasse |

Die folgende Tabelle enthält die standardmäßigen Marshallingregeln, die nur für Windows gelten. Auf Nicht-Windows-Plattformen können Sie diese Typen nicht marshallen.

| .NET-Typ | Nativer Typ (Parameter) | Nativer Typ (Feld) |
|-----------|-------------------------|---------------------|
| `object`  | `VARIANT`               | `IUnknown*`         |
| `System.Array` | COM-Schnittstelle | Ohne `[MarshalAs]`-Attribut nicht zulässig |
| `System.ArgIterator` | `va_list` | Nicht zulässig |
| `System.Collections.IEnumerator` | `IEnumVARIANT*` | Nicht zulässig |
| `System.Collections.IEnumerable` | `IDispatch*` | Nicht zulässig |
| `System.DateTimeOffset` | `int64_t` – repräsentiert die Anzahl von Takten seit dem 1. Januar 1601 um Mitternacht || `int64_t` – repräsentiert die Anzahl von Takten seit dem 1. Januar 1601 um Mitternacht |

Für einige Typen ist das Marshalling nur als Parameter möglich, nicht als Felder. Diese Typen werden in der folgenden Tabelle aufgeführt:

| .NET-Typ | Nativer Typ (nur Parameter) |
|-----------|------------------------------|
| `System.Text.StringBuilder` | Entweder `char*` oder `char16_t*`, je nach `CharSet` von P/Invoke.  Informationen dazu finden Sie in der [Dokumentation zum Zeichensatz](charset.md). |
| `System.ArgIterator` | `va_list` (nur auf Windows x86/x64/arm64) |
| `System.Runtime.InteropServices.ArrayWithOffset` | `void*` |
| `System.Runtime.InteropServices.HandleRef` | `void*` |

Wenn diese Standardwerte nicht exakt Ihren Vorstellungen entsprechen, können Sie angeben, auf welche Weise das Marshalling von Parametern durchgeführt werden soll. Im Artikel [Marshallen von Parametern](customize-parameter-marshaling.md) erfahren Sie, wie Sie das Marshalling verschiedener Parametertypen anpassen.

## <a name="default-marshaling-in-com-scenarios"></a>Standardmarshalling in COM-Szenarien

Wenn Sie Methoden in COM-Objekten in .NET aufrufen, ändert die .NET-Runtime die standardmäßigen Marshallingregeln, um der allgemeinen COM-Semantik zu entsprechen. In der folgenden Tabelle werden die Regeln aufgeführt, die die .NET-Runtime in COM-Szenarien verwendet:

| .NET-Typ | Nativer Typ (COM-Methodenaufrufe) |
|-----------|--------------------------------|
| `bool`    | `VARIANT_BOOL`                 |
| `StringBuilder` | `LPWSTR`                 |
| `string`  | `BSTR`                         |
| Delegattypen | `_Delegate*` in .NET Framework. In .NET Core nicht zulässig. |
| `System.Drawing.Color` | `OLECOLOR`        |
| .NET-Array | `SAFEARRAY`                   |
| `string[]` | `SAFEARRAY` aus `BSTR`s        |

## <a name="marshaling-classes-and-structs"></a>Marshallen von Klassen und Strukturen

Ein weiterer Aspekt des Marshallens von Typen ist die Übergabe einer Struktur an eine nicht verwaltete Methode. Einige der nicht verwalteten Methoden erfordern beispielsweise eine Struktur als Parameter. In diesen Fällen müssen Sie eine entsprechende Struktur oder eine Klasse im verwalteten Bereich erstellen, um sie als Parameter zu verwenden. Allerdings reicht das Definieren der Klasse nicht aus, Sie müssen dem Marshaller außerdem mitteilen, wie Felder in der Klasse der nicht verwalteten Struktur zuzuordnen sind. Hierbei ist das `StructLayout`-Attribut nützlich.

```csharp
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}
```

Der obige Code zeigt ein einfaches Beispiel für einen Aufruf in der `GetSystemTime()`-Funktion. Der interessante Teil befindet sich in Zeile 4. Das Attribut gibt an, dass die Felder der Klasse sequenziell der Struktur auf der anderen (nicht verwalteten) Seite zugeordnet werden sollen. Dies bedeutet, dass die Benennung der Felder nicht wichtig ist, sondern nur deren Reihenfolge, da diese der nicht verwalteten Struktur entsprechen muss, wie im folgenden Beispiel gezeigt:

```c
typedef struct _SYSTEMTIME {
  WORD wYear;
  WORD wMonth;
  WORD wDayOfWeek;
  WORD wDay;
  WORD wHour;
  WORD wMinute;
  WORD wSecond;
  WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME;
```

Manchmal führt das standardmäßige Marshalling für Ihre Struktur nicht zum gewünschten Ergebnis. Im Artikel [Anpassen des Marshallens für Strukturen](./customize-struct-marshaling.md) erfahren Sie, wie Sie das Marshalling für Ihre Struktur anpassen.
