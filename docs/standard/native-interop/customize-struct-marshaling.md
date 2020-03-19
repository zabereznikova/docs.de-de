---
title: Anpassen des Marshallings für Strukturen – .NET
description: Erfahren Sie, wie Sie anpassen können, wie .NET Ihre Strukturen in eine native Darstellung marshallt.
ms.date: 01/18/2019
dev_langs:
- csharp
- cpp
ms.openlocfilehash: 7f8d1ad93633d6feef9c3c6f5d19aad52105968c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401166"
---
# <a name="customizing-structure-marshaling"></a>Anpassen des Marshallings für Strukturen

Manchmal entsprechen die Standardregeln für das Marshallen nicht genau Ihren Anforderungen. Die .NET-Runtimes bieten einige Erweiterungspunkte, mit denen Sie das Layout der Struktur und das Marshallen von Feldern anpassen können.

## <a name="customizing-structure-layout"></a>Anpassen des Strukturlayouts

.NET bietet das <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType>-Attribut und die <xref:System.Runtime.InteropServices.LayoutKind?displayProperty=nameWithType>-Enumeration, damit Sie anpassen können, wie Felder im Arbeitsspeicher abgelegt werden. Die folgende Anleitung hilft Ihnen dabei, gängige Probleme zu vermeiden.

✔️ ERWÄGEN SIE nach Möglichkeit die Verwendung von `LayoutKind.Sequential`.

✔️ VERWENDEN SIE`LayoutKind.Explicit` beim Marshallen nur dann, wenn die native Struktur ebenfalls ein explizites Layout aufweist, beispielsweise eine Union.

❌AVOID `LayoutKind.Explicit` beim Marshallen von Strukturen auf Nicht-Windows-Plattformen, wenn Sie Laufzeiten vor .NET Core 3.0 zielen müssen. Die .NET Core-Laufzeit vor 3.0 unterstützt nicht das Übergeben expliziter Strukturen nach Wert an systemeigene Funktionen auf Intel- oder AMD 64-Bit-Nicht-Windows-Systemen. Die Runtime unterstützt jedoch auf allen Plattformen die Übergabe expliziter Strukturen per Verweis.

## <a name="customizing-boolean-field-marshaling"></a>Anpassen des Marshallens boolescher Felder

Für nativen Code gibt es viele verschiedene boolesche Darstellungen. Allein unter Windows gibt es drei Möglichkeiten zur Darstellung boolescher Werte. Der Runtime ist die native Definition Ihrer Struktur nicht bekannt, daher kann sie allenfalls raten, wie Ihre booleschen Werte gemarshallt werden sollen. Die .NET-Runtime bietet eine Möglichkeit anzugeben, wie Ihr boolesches Feld gemarshallt werden soll. Die folgenden Beispiele zeigen, wie .NET `bool` in andere native boolesche Typen gemarshallt wird.

Boolesche Werte werden standardmäßig als nativer Win32-Wert [`BOOL`](/windows/desktop/winprog/windows-data-types#BOOL) mit 4 Byte gemarshallt, wie im folgenden Beispiel gezeigt:

```csharp
public struct WinBool
{
    public bool b;
}
```

```cpp
struct WinBool
{
    public BOOL b;
};
```

Wenn Sie eine explizite Festlegung treffen möchten, können Sie mit dem Wert <xref:System.Runtime.InteropServices.UnmanagedType.Bool?displayProperty=nameWithType> dasselbe Verhalten wie oben erzielen:

```csharp
public struct WinBool
{
    [MarshalAs(UnmanagedType.Bool)]
    public bool b;
}
```

```cpp
struct WinBool
{
    public BOOL b;
};
```

Mit den unten gezeigten Werten `UnmanagedType.U1` oder `UnmanagedType.I1` können Sie die Runtime anweisen, das `b`-Feld als nativen 1-Byte-`bool`-Typ zu marshallen.

```csharp
public struct CBool
{
    [MarshalAs(UnmanagedType.U1)]
    public bool b;
}
```

```cpp
struct CBool
{
    public bool b;
};
```

Unter Windows können Sie die Runtime mit dem Wert <xref:System.Runtime.InteropServices.UnmanagedType.VariantBool?displayProperty=nameWithType> anweisen, Ihren booleschen Wert in einen 2-Byte-`VARIANT_BOOL`-Wert zu marshallen:

```csharp
public struct VariantBool
{
    [MarshalAs(UnmanagedType.VariantBool)]
    public bool b;
}
```

```cpp
struct VariantBool
{
    public VARIANT_BOOL b;
};
```

> [!NOTE]
> `VARIANT_BOOL` unterscheidet sich von den meisten booleschen Typen insofern als dass `VARIANT_TRUE = -1` und `VARIANT_FALSE = 0` sind. Darüber hinaus werden alle Werte als FALSE betrachtet, die nicht gleich `VARIANT_TRUE` sind.

## <a name="customizing-array-field-marshaling"></a>Anpassen des Marshallens von Arrayfeldern

.NET umfasst auch einige Möglichkeiten zum Anpassen des Marshallens von Arrays.

In der Standardeinstellung marshallt .NET Arrays als Zeiger auf eine zusammenhängende Liste der Elemente:

```csharp
public struct DefaultArray
{
    public int[] values;
}
```

```cpp
struct DefaultArray
{
    int* values;
};
```

Wenn Sie mit COM-APIs arbeiten, müssen Sie Arrays möglicherweise als `SAFEARRAY*`-Objekte marshallen. Mit den Werten <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> und <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> können Sie die Runtime anweisen, ein Array als `SAFEARRAY*` zu marshallen:

```csharp
public struct SafeArrayExample
{
    [MarshalAs(UnmanagedType.SafeArray)]
    public int[] values;
}
```

```cpp
struct SafeArrayExample
{
    SAFEARRAY* values;
};
```

Wenn Sie anpassen möchten, welche Art von Element in `SAFEARRAY` enthalten ist, können Sie mithilfe der Felder <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> und <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> den genauen Elementtyp von `SAFEARRAY` anpassen.

Wenn Sie das Array direkt marshallen möchten, können Sie den Marshaller über den Wert <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType> entsprechend anweisen. Wenn Sie diese Art des Marshallens einsetzen, müssen Sie dem Feld <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> auch einen Wert für die Anzahl von Elementen im Array angeben, damit die Runtime die richtige Speichermenge für die Struktur zuweisen kann.

```csharp
public struct InPlaceArray
{
    [MarshalAs(UnmanagedType.ByValArray, SizeConst = 4)]
    public int[] values;
}
```

```cpp
struct InPlaceArray
{
    int values[4];
};
```

> [!NOTE]
> .NET unterstützt nicht das Marshallen eines Arrayfelds mit variabler Länge als flexibles C99-Arraymember.

## <a name="customizing-string-field-marshaling"></a>Anpassen des Marshallens von Zeichenfolgenfeldern

.NET bietet auch eine Vielzahl von Anpassungen für das Marshallen von Zeichenfolgenfeldern.

In der Standardeinstellung marshallt .NET eine Zeichenfolge als Zeiger auf eine mit NULL beendete Zeichenfolge. Die Codierung hängt von dem Wert des Felds <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> im <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType> ab. Wenn kein Attribut angegeben ist, wird als Codierung standardmäßig die ANSI-Codierung verwendet.

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
public struct DefaultString
{
    public string str;
}
```

```cpp
struct DefaultString
{
    char* str;
};
```

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct DefaultString
{
    public string str;
}
```

```cpp
struct DefaultString
{
    char16_t* str; // Could also be wchar_t* on Windows.
};
```

Wenn Sie unterschiedliche Codierungen für verschiedene Felder verwenden oder Ihre Strukturdefinition einfach expliziter gestalten möchten, können Sie die Werte <xref:System.Runtime.InteropServices.UnmanagedType.LPStr?displayProperty=nameWithType> oder <xref:System.Runtime.InteropServices.UnmanagedType.LPWStr?displayProperty=nameWithType> für ein <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType>-Attribut verwenden.

```csharp
public struct AnsiString
{
    [MarshalAs(UnmanagedType.LPStr)]
    public string str;
}
```

```cpp
struct AnsiString
{
    char* str;
};
```

```csharp
public struct UnicodeString
{
    [MarshalAs(UnmanagedType.LPWStr)]
    public string str;
}
```

```cpp
struct UnicodeString
{
    char16_t* str; // Could also be wchar_t* on Windows.
};
```

Wenn Sie Ihre Zeichenfolgen mit der UTF-8-Codierung marshallen möchten, können Sie den Wert <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> in Ihrem <xref:System.Runtime.InteropServices.MarshalAsAttribute> verwenden.

```csharp
public struct UTF8String
{
    [MarshalAs(UnmanagedType.LPUTF8Str)]
    public string str;
}
```

```cpp
struct UTF8String
{
    char* str;
};
```

> [!NOTE]
> Für die Verwendung von <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> ist entweder .NET Framework 4.7 (oder höher) oder .NET Core 1.1 (oder höher) erforderlich. In .NET Standard 2.0 ist diese Option nicht verfügbar.

Wenn Sie mit COM-APIs arbeiten, müssen Sie eine Zeichenfolge möglicherweise als `BSTR` marshallen. Mit dem Wert <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> können Sie eine Zeichenfolge als `BSTR` marshallen.

```csharp
public struct BString
{
    [MarshalAs(UnmanagedType.BStr)]
    public string str;
}
```

```cpp
struct BString
{
    BSTR str;
};
```

Wenn Sie eine WinRT-basierte API verwenden, müssen Sie eine Zeichenfolge möglicherweise als `HSTRING` marshallen.  Mit dem Wert <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> können Sie eine Zeichenfolge als `HSTRING` marshallen.

```csharp
public struct HString
{
    [MarshalAs(UnmanagedType.HString)]
    public string str;
}
```

```cpp
struct BString
{
    HSTRING str;
};
```

Wenn Ihre API verlangt, dass die Zeichenfolge direkt in der Struktur übergeben werden muss, können Sie den Wert <xref:System.Runtime.InteropServices.UnmanagedType.ByValTStr?displayProperty=nameWithType> verwenden. Beachten Sie, dass die Codierung für eine Zeichenfolge, die mit `ByValTStr` gemarshallt wird, durch das Attribut `CharSet` festgelegt wird. Darüber hinaus muss über das Feld <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> eine Zeichenfolgenlänge übergeben werden.

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
public struct DefaultString
{
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 4)]
    public string str;
}
```

```cpp
struct DefaultString
{
    char str[4];
};
```

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct DefaultString
{
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 4)]
    public string str;
}
```

```cpp
struct DefaultString
{
    char16_t str[4]; // Could also be wchar_t[4] on Windows.
};
```

## <a name="customizing-decimal-field-marshaling"></a>Anpassen des Marshallens von Dezimalfeldern

Wenn Sie unter Windows arbeiten, können einige APIs [ `CY` `CURRENCY` ](/windows/win32/api/wtypes/ns-wtypes-cy~r1) auftreten, die die systemeigene Datei oder Struktur verwenden. Standardmäßig wird der `decimal` .NET-Typ in [`DECIMAL`](/windows/win32/api/wtypes/ns-wtypes-decimal~r1) die systemeigene Struktur gemarshallt. Sie können jedoch ein <xref:System.Runtime.InteropServices.MarshalAsAttribute> mit dem Wert <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=nameWithType> verwenden, um den Marshaller zur Konvertierung eines `decimal`-Werts in einen nativen `CY`-Wert anzuweisen.

```csharp
public struct Currency
{
    [MarshalAs(UnmanagedType.Currency)]
    public decimal dec;
}
```

```cpp
struct Currency
{
    CY dec;
};
```

## <a name="marshaling-systemobjects"></a>Marshalling von `System.Object`

Unter Windows können Sie Felder vom Typ `object` in nativen Code marshallen. Diese Felder können in einen der drei folgenden Typen gemarshallt werden:

- [`VARIANT`](/windows/win32/api/oaidl/ns-oaidl-variant)
- [`IUnknown*`](/windows/desktop/api/unknwn/nn-unknwn-iunknown)
- [`IDispatch*`](/windows/desktop/api/oaidl/nn-oaidl-idispatch)

Standardmäßig wird ein Feld vom Typ `object` in ein `IUnknown*`-Feld gemarshallt, das das Objekt umschließt.

```csharp
public struct ObjectDefault
{
    public object obj;
}
```

```cpp
struct ObjectDefault
{
    IUnknown* obj;
};
```

Wenn Sie ein Objektfeld in `IDispatch*` marshallen möchten, fügen Sie ein <xref:System.Runtime.InteropServices.MarshalAsAttribute> mit dem Wert <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType> hinzu.

```csharp
public struct ObjectDispatch
{
    [MarshalAs(UnmanagedType.IDispatch)]
    public object obj;
}
```

```cpp
struct ObjectDispatch
{
    IDispatch* obj;
};
```

Wenn Sie es als `VARIANT` marshallen möchten, fügen Sie ein <xref:System.Runtime.InteropServices.MarshalAsAttribute> mit dem Wert <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> hinzu.

```csharp
public struct ObjectVariant
{
    [MarshalAs(UnmanagedType.Struct)]
    public object obj;
}
```

```cpp
struct ObjectVariant
{
    VARIANT obj;
};
```

In der folgenden Tabelle wird beschrieben, wie verschiedene Runtimetypen des Felds `obj` den verschiedenen Typen zugeordnet werden können, die in `VARIANT` gespeichert sind:

| .NET-Typ | VARIANT-Typ | | .NET-Typ | VARIANT-Typ |
|------------|--------------|-|----------|--------------|
|  `byte`  | `VT_UI1` |     | `System.Runtime.InteropServices.BStrWrapper` | `VT_BSTR` |
| `sbyte`  | `VT_I1`  |     | `object`  | `VT_DISPATCH` |
| `short`  | `VT_I2`  |     | `System.Runtime.InteropServices.UnknownWrapper` | `VT_UNKNOWN` |
| `ushort` | `VT_UI2` |     | `System.Runtime.InteropServices.DispatchWrapper` | `VT_DISPATCH` |
| `int`    | `VT_I4`  |     | `System.Reflection.Missing` | `VT_ERROR` |
| `uint`   | `VT_UI4` |     | `(object)null` | `VT_EMPTY` |
| `long`   | `VT_I8`  |     | `bool` | `VT_BOOL` |
| `ulong`  | `VT_UI8` |     | `System.DateTime` | `VT_DATE` |
| `float`  | `VT_R4`  |     | `decimal` | `VT_DECIMAL` |
| `double` | `VT_R8`  |     | `System.Runtime.InteropServices.CurrencyWrapper` | `VT_CURRENCY` |
| `char`   | `VT_UI2` |     | `System.DBNull` | `VT_NULL` |
| `string` | `VT_BSTR`|
