---
title: Standardmäßiges Marshalling für Objekte
description: Machen Sie sich mit dem standardmäßigen Marshalling für Objekte vertraut. Überprüfen Sie Marshallingoptionen. Marshallen Sie Objekte zu Schnittstellen oder Varianten, Varianten zu Objekten und ByRef-Varianten.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- objects, interop marshaling
- interop marshaling, objects
ms.assetid: c2ef0284-b061-4e12-b6d3-6a502b9cc558
ms.openlocfilehash: 7b8f94f4dfd8e8b9e8e04df8de5f8266a8581a92
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618452"
---
# <a name="default-marshaling-for-objects"></a>Standardmäßiges Marshalling für Objekte

Parameter und Felder, die als <xref:System.Object?displayProperty=nameWithType> typisiert sind, können für nicht verwalteten Code als einer der folgenden Typen verfügbar gemacht werden:

- Als Variante, wenn das Objekt ein Parameter ist.

- Als Schnittstelle, wenn das Objekt ein Strukturfeld ist.

Nur COM-Interop unterstützt das Marshallen von Objekttypen. Standardmäßig werden Objekte an COM-Varianten gemarshallt. Diese Regeln gelten nur für den Typ **Objekt** und gelten nicht für stark typisierte Objekte, die von der **Objekt**-Klasse abgeleitet werden.

## <a name="marshaling-options"></a>Marshallingoptionen

Die folgende Tabelle zeigt die Marshalling-Optionen für den **Objekt**-Datentyp. Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut stellt mehrere <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswerte zum Marshallen von Objekten bereit.

|Enumerationstyp|Beschreibung des nicht verwalteten Formats|
|----------------------|-------------------------------------|
|**UnmanagedType.Struct**<br /><br /> (Standard für Parameter)|Eine Variante im COM-Stil.|
|**UnmanagedType.Interface**|Eine **IDispatch**-Schnittstelle, wenn möglich, andernfalls eine **IUnknown**-Schnittstelle.|
|**UnmanagedType.IUnknown**<br /><br /> (Standard für Felder)|Eine **IUnknown**-Schnittstelle.|
|**UnmanagedType.IDispatch**|Eine **IDispatch**-Schnittstelle.|

Das folgende Beispiel zeigt die verwaltete Schnittstellendefinition für `MarshalObject`.

```vb
Interface MarshalObject
   Sub SetVariant(o As Object)
   Sub SetVariantRef(ByRef o As Object)
   Function GetVariant() As Object

   Sub SetIDispatch( <MarshalAs(UnmanagedType.IDispatch)> o As Object)
   Sub SetIDispatchRef(ByRef <MarshalAs(UnmanagedType.IDispatch)> o _
      As Object)
   Function GetIDispatch() As <MarshalAs(UnmanagedType.IDispatch)> Object
   Sub SetIUnknown( <MarshalAs(UnmanagedType.IUnknown)> o As Object)
   Sub SetIUnknownRef(ByRef <MarshalAs(UnmanagedType.IUnknown)> o _
      As Object)
   Function GetIUnknown() As <MarshalAs(UnmanagedType.IUnknown)> Object
End Interface
```

```csharp
interface MarshalObject {
   void SetVariant(Object o);
   void SetVariantRef(ref Object o);
   Object GetVariant();

   void SetIDispatch ([MarshalAs(UnmanagedType.IDispatch)]Object o);
   void SetIDispatchRef([MarshalAs(UnmanagedType.IDispatch)]ref Object o);
   [MarshalAs(UnmanagedType.IDispatch)] Object GetIDispatch();
   void SetIUnknown ([MarshalAs(UnmanagedType.IUnknown)]Object o);
   void SetIUnknownRef([MarshalAs(UnmanagedType.IUnknown)]ref Object o);
   [MarshalAs(UnmanagedType.IUnknown)] Object GetIUnknown();
}
```

Der folgende Code exportiert die `MarshalObject` Schnittstelle in eine Typbibliothek.

```cpp
interface MarshalObject {
   HRESULT SetVariant([in] VARIANT o);
   HRESULT SetVariantRef([in,out] VARIANT *o);
   HRESULT GetVariant([out,retval] VARIANT *o)
   HRESULT SetIDispatch([in] IDispatch *o);
   HRESULT SetIDispatchRef([in,out] IDispatch **o);
   HRESULT GetIDispatch([out,retval] IDispatch **o)
   HRESULT SetIUnknown([in] IUnknown *o);
   HRESULT SetIUnknownRef([in,out] IUnknown **o);
   HRESULT GetIUnknown([out,retval] IUnknown **o)
}
```

> [!NOTE]
> Der Interop-Marshaller gibt nach dem Aufruf automatisch alle zugeordneten Objekte innerhalb der Variante frei.

Das folgende Beispiel zeigt einen formatierten Werttypen.

```vb
Public Structure ObjectHolder
   Dim o1 As Object
   <MarshalAs(UnmanagedType.IDispatch)> Public o2 As Object
End Structure
```

```csharp
public struct ObjectHolder {
   Object o1;
   [MarshalAs(UnmanagedType.IDispatch)]public Object o2;
}
```

Der folgende Code exportiert den formatierten Typ in eine Typbibliothek.

```cpp
struct ObjectHolder {
   VARIANT o1;
   IDispatch *o2;
}
```

## <a name="marshaling-object-to-interface"></a>Marshalling eines Objekts an eine Schnittstelle

Wenn ein Objekt in COM als Schnittstelle verfügbar gemacht wird, ist diese Schnittstelle die Klassenschnittstelle für den verwalteten Typ <xref:System.Object> (die **_Object**-Schnittstelle). Diese Schnittstelle wird als **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) oder als **IUnknown** (**UnmanagedType.IUnknown**) in der resultierenden Typbibliothek typisiert. COM-Clients können die Mitglieder der verwalteten Klasse, oder irgendwelche Mitglieder, die durch die abgeleiteten Klassen über die **_Object**-Schnittstelle implementiert wurden dynamisch abrufen. Der Client kann auch **QueryInterface** aufrufen, um irgendeine andere Schnittstelle zu erhalten, die vom verwalteten Typ explizit implementiert wurde.

## <a name="marshaling-object-to-variant"></a>Marshalling eines Objekts an eine Variante

Wenn ein Objekt an eine Variante gemarshallt wird, wird der interne Varianttyp zur Laufzeit anhand der folgenden Regeln bestimmt:

- Wenn der Objektverweis NULL ist (**Nothing** (nichts) in Visual Basic), wird das Objekt an eine Variante des Typs **VT_EMPTY** gemarshallt.

- Wenn das Objekt eine Instanz eines beliebigen Typs ist, die in der folgenden Tabelle aufgeführt ist, wird der resultierende Varianttyp durch die im Marshaller integrierten und in der Tabelle aufgeführten Regeln bestimmt.

- Andere Objekte, die das Marshalling-Verhalten explizit steuern müssen, können die <xref:System.IConvertible>-Schnittstelle implementieren. In diesem Fall wird der Varianttyp durch den Typcode bestimmt, der von der <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>-Methode zurückgegeben wird. Andernfalls wird das Objekt als eine Variante des Typs **VT_UNKNOWN** gemarshallt.

### <a name="marshaling-system-types-to-variant"></a>Marshalling von Systemtypen an Varianten

Die folgende Tabelle zeigt verwaltete Objekttypen und ihre entsprechenden COM-Varianttypen. Diese Typen werden nur konvertiert, wenn die Signatur der aufgerufenen Methode vom Typ <xref:System.Object?displayProperty=nameWithType> ist.

|Objekttyp|COM-Varianttyp|
|-----------------|----------------------|
|NULL-Objektverweis (**Nothing** (nichts) in Visual&#160;Basic).|**VT_EMPTY**|
|<xref:System.DBNull?displayProperty=nameWithType>|**VT_NULL**|
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|**VT_ERROR**|
|<xref:System.Reflection.Missing?displayProperty=nameWithType>|**VT_ERROR** mit **E_PARAMNOTFOUND**|
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|**VT_DISPATCH**|
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|**VT_UNKNOWN**|
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|**VT_CY**|
|<xref:System.Boolean?displayProperty=nameWithType>|**VT_BOOL**|
|<xref:System.SByte?displayProperty=nameWithType>|**VT_I1**|
|<xref:System.Byte?displayProperty=nameWithType>|**VT_UI1**|
|<xref:System.Int16?displayProperty=nameWithType>|**VT_I2**|
|<xref:System.UInt16?displayProperty=nameWithType>|**VT_UI2**|
|<xref:System.Int32?displayProperty=nameWithType>|**VT_I4**|
|<xref:System.UInt32?displayProperty=nameWithType>|**VT_UI4**|
|<xref:System.Int64?displayProperty=nameWithType>|**VT_I8**|
|<xref:System.UInt64?displayProperty=nameWithType>|**VT_UI8**|
|<xref:System.Single?displayProperty=nameWithType>|**VT_R4**|
|<xref:System.Double?displayProperty=nameWithType>|**VT_R8**|
|<xref:System.Decimal?displayProperty=nameWithType>|**VT_DECIMAL**|
|<xref:System.DateTime?displayProperty=nameWithType>|**VT_DATE**|
|<xref:System.String?displayProperty=nameWithType>|**VT_BSTR**|
|<xref:System.IntPtr?displayProperty=nameWithType>|**VT_INT**|
|<xref:System.UIntPtr?displayProperty=nameWithType>|**VT_UINT**|
|<xref:System.Array?displayProperty=nameWithType>|**VT_ARRAY**|

Mithilfe der im vorherigen Beispiel definierten `MarshalObject`-Schnittstelle, veranschaulicht das folgende Codebeispiel, wie unterschiedliche Varianttypen an einen COM-Server übergeben werden.

```vb
Dim mo As New MarshalObject()
mo.SetVariant(Nothing)         ' Marshal as variant of type VT_EMPTY.
mo.SetVariant(System.DBNull.Value) ' Marshal as variant of type VT_NULL.
mo.SetVariant(CInt(27))        ' Marshal as variant of type VT_I2.
mo.SetVariant(CLng(27))        ' Marshal as variant of type VT_I4.
mo.SetVariant(CSng(27.0))      ' Marshal as variant of type VT_R4.
mo.SetVariant(CDbl(27.0))      ' Marshal as variant of type VT_R8.
```

```csharp
MarshalObject mo = new MarshalObject();
mo.SetVariant(null);            // Marshal as variant of type VT_EMPTY.
mo.SetVariant(System.DBNull.Value); // Marshal as variant of type VT_NULL.
mo.SetVariant((int)27);          // Marshal as variant of type VT_I2.
mo.SetVariant((long)27);          // Marshal as variant of type VT_I4.
mo.SetVariant((single)27.0);   // Marshal as variant of type VT_R4.
mo.SetVariant((double)27.0);   // Marshal as variant of type VT_R8.
```

COM-Typen, die keine entsprechenden verwalteten Typen aufweisen, können mithilfe von Wrapperklassen, z.B. <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper>, und <xref:System.Runtime.InteropServices.CurrencyWrapper> gemarshallt werden. Das folgende Codebeispiel veranschaulicht, wie diese unterschiedlichen Wrapper verwendet werden, um verschiedene Varianttypen an einen COM-Server zu übergeben.

```vb
Imports System.Runtime.InteropServices
' Pass inew as a variant of type VT_UNKNOWN interface.
mo.SetVariant(New UnknownWrapper(inew))
' Pass inew as a variant of type VT_DISPATCH interface.
mo.SetVariant(New DispatchWrapper(inew))
' Pass a value as a variant of type VT_ERROR interface.
mo.SetVariant(New ErrorWrapper(&H80054002))
' Pass a value as a variant of type VT_CURRENCY interface.
mo.SetVariant(New CurrencyWrapper(New Decimal(5.25)))
```

```csharp
using System.Runtime.InteropServices;
// Pass inew as a variant of type VT_UNKNOWN interface.
mo.SetVariant(new UnknownWrapper(inew));
// Pass inew as a variant of type VT_DISPATCH interface.
mo.SetVariant(new DispatchWrapper(inew));
// Pass a value as a variant of type VT_ERROR interface.
mo.SetVariant(new ErrorWrapper(0x80054002));
// Pass a value as a variant of type VT_CURRENCY interface.
mo.SetVariant(new CurrencyWrapper(new Decimal(5.25)));
```

Die Wrapperklassen werden im <xref:System.Runtime.InteropServices>-Namespace definiert.

### <a name="marshaling-the-iconvertible-interface-to-variant"></a>Marshalling der IConvertible-Schnittstelle an eine Variante

Typen, die im vorherigen Abschnitt nicht aufgeführt werden, können durch Implementierung der <xref:System.IConvertible>-Schnittstelle steuern, wie sie gemarshallt werden. Wenn das Objekt die **IConvertible**-Schnittstelle implementiert, wird der COM-Varianttyp zur Laufzeit durch den Wert der durch die <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>-Methode zurückgegeben <xref:System.TypeCode>-Enumeration bestimmt.

Die folgende Tabelle zeigt die möglichen Werte für die **TypeCode**-Enumeration und die entsprechenden COM-Varianttypen für jeden Wert.

|TypeCode|COM-Varianttyp|
|--------------|----------------------|
|**TypeCode.Empty**|**VT_EMPTY**|
|**TypeCode.Object**|**VT_UNKNOWN**|
|**TypeCode.DBNULL**|**VT_NULL**|
|**TypeCode.Boolean**|**VT_BOOL**|
|**TypeCode.Char**|**VT_UI2**|
|**TypeCode.Sbyte**|**VT_I1**|
|**TypeCode.Byte**|**VT_UI1**|
|**TypeCode.Int16**|**VT_I2**|
|**TypeCode.UInt16**|**VT_UI2**|
|**TypeCode.Int32**|**VT_I4**|
|**TypeCode.UInt32**|**VT_UI4**|
|**TypeCode.Int64**|**VT_I8**|
|**TypeCode.UInt64**|**VT_UI8**|
|**TypeCode.Single**|**VT_R4**|
|**TypeCode.Double**|**VT_R8**|
|**TypeCode.Decimal**|**VT_DECIMAL**|
|**TypeCode.DateTime**|**VT_DATE**|
|**TypeCode.String**|**VT_BSTR**|
|Wird nicht unterstützt.|**VT_INT**|
|Wird nicht unterstützt.|**VT_UINT**|
|Wird nicht unterstützt.|**VT_ARRAY**|
|Wird nicht unterstützt.|**VT_RECORD**|
|Wird nicht unterstützt.|**VT_CY**|
|Wird nicht unterstützt.|**VT_VARIANT**|

Der Wert der COM-Variante wird durch Aufruf der **IConvertible.To** *Type*-Schnittstelle bestimmt, wobei **To** *Type* die Konvertierungsroutine ist, die dem Typ entspricht, der von **IConvertible.GetTypeCode** zurückgegeben wurde. Beispielsweise ist ein Objekt, das **TypeCode.Double** aus **IConvertible.GetTypeCode** zurückgibt, als COM-Variante des Typs **VT_R8** gemarshallt. Sie erhalten den Wert der Variante (gespeichert im **DblVal**-Feld der COM-Variante), indem Sie eine Umwandlung in die **IConvertible**-Schnittstelle durchführen und die <xref:System.IConvertible.ToDouble%2A>-Methode aufrufen.

## <a name="marshaling-variant-to-object"></a>Marshalling einer Variante an ein Objekt

Beim Marshallen einer Variante an ein Objekt bestimmt der Typ und in einigen Fällen der Wert der gemarshallten Variante den Typ des erstellten Objekts. In der folgenden Tabelle sind die einzelnen Varianttypen und die entsprechenden Objekttypen aufgelistet, die der Marshaller erstellt, wenn eine Variante aus COM an .NET Framework übergeben wird.

|COM-Varianttyp|Objekttyp|
|----------------------|-----------------|
|**VT_EMPTY**|NULL-Objektverweis (**Nothing** (nichts) in Visual Basic).|
|**VT_NULL**|<xref:System.DBNull?displayProperty=nameWithType>|
|**VT_DISPATCH**|**System.__ComObject** oder NULL wenn (pdispVal == NULL)|
|**VT_UNKNOWN**|**System.__ComObject** oder NULL wenn (punkVal == NULL)|
|**VT_ERROR**|<xref:System.UInt32?displayProperty=nameWithType>|
|**VT_BOOL**|<xref:System.Boolean?displayProperty=nameWithType>|
|**VT_I1**|<xref:System.SByte?displayProperty=nameWithType>|
|**VT_UI1**|<xref:System.Byte?displayProperty=nameWithType>|
|**VT_I2**|<xref:System.Int16?displayProperty=nameWithType>|
|**VT_UI2**|<xref:System.UInt16?displayProperty=nameWithType>|
|**VT_I4**|<xref:System.Int32?displayProperty=nameWithType>|
|**VT_UI4**|<xref:System.UInt32?displayProperty=nameWithType>|
|**VT_I8**|<xref:System.Int64?displayProperty=nameWithType>|
|**VT_UI8**|<xref:System.UInt64?displayProperty=nameWithType>|
|**VT_R4**|<xref:System.Single?displayProperty=nameWithType>|
|**VT_R8**|<xref:System.Double?displayProperty=nameWithType>|
|**VT_DECIMAL**|<xref:System.Decimal?displayProperty=nameWithType>|
|**VT_DATE**|<xref:System.DateTime?displayProperty=nameWithType>|
|**VT_BSTR**|<xref:System.String?displayProperty=nameWithType>|
|**VT_INT**|<xref:System.Int32?displayProperty=nameWithType>|
|**VT_UINT**|<xref:System.UInt32?displayProperty=nameWithType>|
|**VT_ARRAY** &#124; **VT_** \*|<xref:System.Array?displayProperty=nameWithType>|
|**VT_CY**|<xref:System.Decimal?displayProperty=nameWithType>|
|**VT_RECORD**|Entsprechender geschachtelter Werttyp.|
|**VT_VARIANT**|Wird nicht unterstützt.|

Varianttypen aus COM, die an verwalteten Code übergeben und dann an COM zurückgegeben werden, behalten für die Dauer des Aufrufs möglicherweise nicht denselben Varianttypen bei. Beachten Sie, was geschieht, wenn eine Variante des Typs **VT_DISPATCH** von COM an .NET Framework übergeben wird. Während des Marshallens wird die Variante in ein <xref:System.Object?displayProperty=nameWithType> konvertiert. Wenn das **Objekt** dann an COM übergeben wird, wird es wieder auf eine Variante des Typs **VT_UNKNOWN** gemarshallt. Es gibt keine Garantie dafür, dass die erzeugte Variante, wenn ein Objekt an COM aus verwaltetem Code gemarshallt wird vom selben Typ ist, wie die ursprünglich zur Erstellung des Objekts verwendete Variante.

## <a name="marshaling-byref-variants"></a>Marshalling von ByRef-Varianten

Obwohl Varianten selbst durch einen Wert oder durch einen Verweis übergeben werden können, kann das **VT_BYREF**-Flag auch mit einem beliebigen Varianttyp verwendet werden, um anzugeben, dass die Inhalte der Variante durch Verweis und nicht durch einen Wert übergeben werden. Der Unterschied zwischen dem Marshalling von Varianten durch einen Verweis und dem Marshalling von Varianten mit eingerichtetem **VT_BYREF**-Flag kann verwirrend sein. Die folgende Abbildung verdeutlicht die Unterschiede:

![Diagramm einer an den Stapel übergebenen Variante](./media/default-marshaling-for-objects/interop-variant-passed-value-reference.gif)
Durch einen Wert und durch einen Verweis übergebene Varianten

**Standardmäßiges Verhalten beim Marshalling von Objekten und Varianten durch einen Wert**

- Wenn Objekte aus verwaltetem Code an COM übergeben werden, wird der Inhalt des Objekts in eine neue, vom Marshaller erstellte Variante kopiert, unter Verwendung der unter [Marshalling eines Objekts an eine Variante](#marshaling-object-to-variant) definierten Regeln. Die auf der nicht verwalteten Seite der Variante vorgenommenen Änderungen, werden bei Rückgabe aus dem Aufruf nicht auf das ursprüngliche Objekt zurückübertragen.

- Wenn Varianten von COM an verwalteten Code übergeben werden, wird der Inhalt der Variante in ein neu erstelltes Objekt kopiert, unter Verwendung der unter [Marshalling einer Variante an ein Objekt](#marshaling-variant-to-object) definierten Regeln. Die auf der verwalteten Seite des Objekts vorgenommenen Änderungen, werden bei Rückgabe aus dem Aufruf nicht auf die ursprüngliche Variante zurückübertragen.

**Standardverhalten für das Marshalling von Objekten und Varianten durch einen Verweis**

Um Änderungen an den Aufrufer weiterzugeben, müssen die Parameter durch einen Verweis übergeben werden. Beispielsweise können Sie das **Ref**-Schlüsselwort in C# (oder **ByRef** in Visual Basic verwaltetem Code) zum Übergeben von Parametern durch einen Verweis verwenden. In COM werden Verweisparameter mithilfe eines Zeigers, z.B. als **Variante\*** übergeben.

- Wenn ein Objekt durch einen Verweis an COM übergeben wird, erstellt der Marshaller eine neue Variante und kopiert den Inhalt des Objektverweises in die Variante, bevor der Aufruf ausgeführt wird. Die Variante wird an die nicht verwaltete Funktion übergeben, in der der Benutzer den Inhalt der Variante nach Belieben ändern kann. Die auf der nicht verwalteten Seite der Variante vorgenommenen Änderungen, werden bei Rückgabe aus dem Aufruf nicht auf das ursprüngliche Objekt zurückübertragen. Wenn der Typ der Variante vom Typ der an den Aufruf übergebenen Variante abweicht, werden die Änderungen auf ein Objekt eines anderen Typs zurückübertragen. Das bedeutet, dass sich der Typ des an den Aufruf übergeben Objekts vom Typ des Objekts unterscheiden kann, der aus dem Aufruf zurückgegeben wurde.

- Wenn eine Variante durch einen Verweis an verwalteten Code übergeben wird, erstellt der Marshaller ein neues Objekt, und kopiert den Inhalt der Variante in das Objekt, bevor der Aufruf ausgeführt wird. Ein Verweis auf das Objekt wird an die verwaltete Funktion übergeben, in der der Benutzer das Objekt nach Belieben ändern kann. Die am referenzierten Objekt vorgenommenen Änderungen werden bei Rückgabe aus dem Aufruf auf die ursprüngliche Variante zurückübertragen. Wenn sich der Typ des Objekts vom Typ des an den Aufruf übergebenen Objekts unterscheidet, wird der Typ der ursprünglichen Variante geändert, und der Wert wird wieder an die Variante zurückübertragen. Das bedeutet, dass sich der Typ der an den Aufruf übergebenen Variante vom Typ der durch den Aufruf zurückgegebenen Variante unterscheiden kann.

 **Standardverhalten für das Marshalling von Varianten mit eingerichtetem VT_BYREF-Flag**

- Für eine durch einen Wert an verwalteten Code übergebene Variante, kann das **VT_BYREF**-Flag so festgelegt sein, dass angegeben wird, dass die Variante einen Verweis anstelle eines Werts enthält. In diesem Fall wird die Variante noch auf ein Objekt gemarshallt, da die Variante als Wert übergeben wird. Der Marshaller dereferenziert den Inhalt der Variante automatisch und kopiert sie vor der Ausführung des Aufrufs in ein neu erstelltes Objekt. Das Objekt wird dann in die verwaltete Funktion übergeben. Bei der Rückgabe aus dem Aufruf wird das Objekt jedoch nicht wieder in der ursprünglichen Variante zurückverteilt. Am verwalteten Objekt vorgenommene Änderungen gehen verloren.

  > [!CAUTION]
  > Es gibt keine Möglichkeit, den Wert einer Variante, die als Wert übergeben wurde zu ändern, selbst wenn für die Variante das **VT_BYREF**-Flag festgelegt wurde.

- Für eine durch einen Verweis an verwalteten Code übergebene Variante, kann das **VT_BYREF**-Flag so festgelegt sein, dass angegeben wird, dass die Variante einen weiteren Verweis enthält. In diesem Fall wird die Variante noch auf ein **ref**-Objekt gemarshallt, da die Variante durch Verweis übergeben wird. Der Marshaller dereferenziert den Inhalt der Variante automatisch und kopiert sie vor der Ausführung des Aufrufs in ein neu erstelltes Objekt. Bei der Rückgabe des Aufrufs wird der Wert des Objekts zurück an den Verweis in der ursprünglichen Variante nur weitergegeben, wenn das Objekt demselben Typ angehört wie das übergebene Objekt. Durch die Weitergabe wird also der Typ einer Variante mit dem eingerichteten **VT_BYREF**-Flag ändert. Wenn der Objekttyp während des Aufrufs geändert wird, wird bei Rückgabe aus dem Aufruf eine <xref:System.InvalidCastException> ausgelöst.

In der folgenden Tabelle werden die Regeln zur Weitergabe für Varianten und Objekte zusammengefasst.

|Von|Beschreibung|Zurückübertragene Änderungen|
|----------|--------|-----------------------------|
|**Variant** *v*|**Object** *o*|Nie|
|**Object** *o*|**Variant** *v*|Nie|
|**Variant** ***\**** *pv*|**Ref Object** *o*|Always|
|**Ref object** *o*|**Variant** ***\**** *pv*|Always|
|**Variant** *v* **(VT_BYREF** *&#124;* **VT_\*)**|**Object** *o*|Nie|
|**Variant** *v* **(VT_BYREF** *&#124;* **VT_)**|**Ref Object** *o*|Nur, wenn sich der Typ nicht geändert hat.|

## <a name="see-also"></a>Siehe auch

- [Default Marshaling Behavior (Standardmäßiges Marshallingverhalten)](default-marshaling-behavior.md)
- [Blitfähige und nicht blitfähige Typen](blittable-and-non-blittable-types.md)
- [Direktionale Attribute](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))
- [Kopieren und Fixieren](copying-and-pinning.md)
