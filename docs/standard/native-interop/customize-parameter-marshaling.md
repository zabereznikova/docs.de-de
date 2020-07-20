---
title: Anpassen des Marshallings für Parameter – .NET
description: Erfahren Sie, wie Sie anpassen können, wie .NET Ihre Parameter in eine native Darstellung marshallt.
ms.date: 01/18/2019
ms.openlocfilehash: 1999cad057875f15b283421f87f485c2e5ca2306
ms.sourcegitcommit: e7748001b1cee80ced691d8a76ca814c0b02dd9b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86374311"
---
# <a name="customizing-parameter-marshaling"></a>Anpassen des Marshallings für Parameter

Wenn das standardmäßige Verhalten der .NET-Runtime beim Parametermarshalling nicht Ihren Vorstellungen entspricht, können Sie mithilfe des Attributs <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> anpassen, wie Ihre Parameter gemarshallt werden.

## <a name="customizing-string-parameters"></a>Anpassen von Zeichenfolgenparametern

.NET bietet eine Vielzahl von Formaten zum Marshalling von Zeichenfolgen. Diese Methoden werden in unterschiedliche Abschnitte für Zeichenfolgen im C-Stil und für Windows-orientierte Zeichenfolgenformate aufgeteilt.

### <a name="c-style-strings"></a>Zeichenfolgen im C-Stil

Jedes dieser Formate übergibt eine null-terminierte Zeichenkette an den nativen Code. Sie unterscheiden sich hinsichtlich der Codierung der nativen Zeichenfolge.

| `System.Runtime.InteropServices.UnmanagedType`-Wert | Codierung |
|------------------------------------------------------|----------|
| LPStr | ANSI |
| LPUTF8Str | UTF-8 |
| LPWStr | UTF-16 |
| LPTStr | UTF-16 |

Das <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=nameWithType>-Format ist etwas anders. Genauso wie `LPWStr` marshallt es die Zeichenfolge in eine native C-Stil-Zeichenfolge, die in UTF-16 codiert ist. Die verwaltete Signatur lässt Sie jedoch die Zeichenfolge nach Referenz übergeben und die passende native Signatur übernimmt die Zeichenfolge nach Wert. Diese Unterscheidung ermöglicht es Ihnen, eine native API zu verwenden, die eine Zeichenfolge nach Wert übernimmt und an Ort und Stelle ändert, ohne einen `StringBuilder` verwenden zu müssen. Wir empfehlen, dieses Format nicht manuell zu verwenden, da es zu Verwechslungen mit den nicht übereinstimmenden nativen und verwalteten Signaturen führen kann.

### <a name="windows-centric-string-formats"></a>Windows-orientierte Zeichenfolgenformate

Wenn Sie mit COM- oder OLE-Schnittstellen interagieren, werden Sie wahrscheinlich feststellen, dass die nativen Funktionen Zeichenfolgen als `BSTR`-Argumente verwenden. Sie können den nicht verwalteten Typ <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> verwenden, um eine Zeichenfolge als `BSTR` zu marshallen.

Wenn Sie mit WinRT-APIs interagieren, können Sie das Format <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> verwenden, um eine Zeichenfolge als `HSTRING` marshallen.

## <a name="customizing-array-parameters"></a>Anpassen von Arrayparametern

.NET bietet Ihnen außerdem mehrere Möglichkeiten zum Marshallen von Arrayparametern. Wenn Sie eine API aufrufen, die ein Array im C-Stil verwendet, verwenden Sie den nicht verwalteten Typ <xref:System.Runtime.InteropServices.UnmanagedType.LPArray?displayProperty=nameWithType>. Wenn die Werte im Array benutzerdefiniertes Marshalling benötigen, können Sie dafür das Feld <xref:System.Runtime.InteropServices.MarshalAsAttribute.ArraySubType> im Attribut `[MarshalAs]` verwenden.

Wenn Sie COM-APIs verwenden, müssen Sie Ihre Arrayparameter wahrscheinlich als `SAFEARRAY*` marshallen. Dafür können Sie den nicht verwalteten Typ <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> verwenden. Der Standardtyp der Elemente von `SAFEARRAY` werden in der Tabelle in den Feldern [Anpassen`object` angezeigt](./customize-struct-marshaling.md#marshal-systemobject). Sie können die Felder <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> und <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> verwenden, um den genauen Elementtyp von `SAFEARRAY` anzupassen.

## <a name="customizing-boolean-or-decimal-parameters"></a>Anpassen von booleschen oder dezimalen Parametern

Informationen zum Marshalling boolescher oder dezimaler Parameter finden Sie unter [Anpassen des Marshallings für Strukturen](customize-struct-marshaling.md).

## <a name="customizing-object-parameters-windows-only"></a>Anpassen der Objektparameter (nur Windows)

Unter Windows bietet die.NET-Runtime eine Reihe von verschiedenen Möglichkeiten zum Marshallen von Objektparametern in nativen Code.

### <a name="marshaling-as-specific-com-interfaces"></a>Marshalling als bestimmte COM-Schnittstellen

Wenn Ihre API einen Zeiger auf ein COM-Objekt übernimmt, können Sie eines der folgenden `UnmanagedType`-Formate auf einem `object`-typisierten Parameter verwenden, damit .NET als diese spezifischen Schnittstellen marshallt.

- `IUnknown`
- `IDispatch`
- `IInspectable`

Wenn Ihr Typ außerdem mit `[ComVisible(true)]` markiert ist oder Sie ein Marshalling des Typs `object` durchführen, können Sie das Format <xref:System.Runtime.InteropServices.UnmanagedType.Interface?displayProperty=nameWithType> verwenden, um Ihr Objekt als COM Callable Wrapper für die COM-Ansicht Ihres Typs darzustellen.

### <a name="marshaling-to-a-variant"></a>Marshalling zu einer `VARIANT`

Wenn Ihre native API eine Win32-`VARIANT` verwendet, können Sie das <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType>-Format für Ihren `object`-Parameter verwenden, um Ihre Objekte als `VARIANT` zu marshallen. Informationen zur Zuordnung zwischen .NET-Typen und `VARIANT`-Typen finden Sie in der Dokumentation zum [Anpassen von `object`-Feldern](customize-struct-marshaling.md#marshal-systemobject).

### <a name="custom-marshalers"></a>Benutzerdefinierte Marshaller

Wenn Sie eine native COM-Schnittstelle in einen anderen verwalteten Typ projizieren möchten, können Sie das Format `UnmanagedType.CustomMarshaler` und eine Implementierung von <xref:System.Runtime.InteropServices.ICustomMarshaler> verwenden, um Ihren eigenen benutzerdefinierten Marshallingcode bereitzustellen.
