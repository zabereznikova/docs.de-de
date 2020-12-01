---
title: Standardmäßiges Marshalling für Arrays
description: Machen Sie sich mit dem standardmäßigen Marshalling für Arrays vertraut. Erfahren Sie mehr über verwaltete Arrays, nicht verwaltete Arrays, das Übergeben von Arrayparametern an .NET-Code und das Übergeben von Arrays an COM.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, arrays
- arrays, interop marshaling
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
ms.openlocfilehash: b6a675bbbfb974d78539d02b31b500b03a2ac8f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256660"
---
# <a name="default-marshaling-for-arrays"></a>Standardmäßiges Marshalling für Arrays

In einer Anwendung, die vollständig aus verwaltetem Code besteht, übergibt die Common Language Runtime Arraytypen als In-/Out-Parameter. Im Gegensatz dazu übergibt der Interopmarshaller außerdem ein Array als In-Parameter in der Standardeinstellung.  
  
 Bei der [pinning optimization](copying-and-pinning.md) (Fixierungsoptimierung),kann ein blitfähiges Array den Anschein erwecken, dass es als In/Out-Parameter fungiert, wenn es mit Objekten in demselben Apartment interagiert. Wenn Sie allerdings den Code später in eine Typbibliothek exportieren, mit der der computerübergreifende Proxy generiert wird, und diese Bibliothek dazu verwendet wird, Ihre Aufrufe über Apartments hinweg zu marshallen, können sich die Aufrufe wieder wie TRUE-Parameter verhalten.  
  
 Arrays sind naturgemäß komplex, und die Unterschiede zwischen verwalteten und nicht verwalteten Arrays bieten mehr Informationen als andere nicht blitfähige Typen.  
  
## <a name="managed-arrays"></a>Verwaltete Arrays  

 Verwaltete Arraytypen können variieren. Allerdings ist die <xref:System.Array?displayProperty=nameWithType>-Klasse die Basisklasse für alle Arraytypen. Die **System.Array**-Klasse enthält Eigenschaften, um den Rang, die Länge und die Unter- und Obergrenze eines Arrays zu bestimmen, als auch Methoden zum Zugreifen, Sortieren, Durchsuchen, Kopieren und Erstellen von Arrays.  
  
 Diese Arraytypen sind dynamisch und verfügen über keinen entsprechenden statischen, in der Basisklassenbibliothek definierten Typen. Es ist sinnvoll, jede Kombination aus Elementtyp und Rang als gesonderten Arraytypen zu betrachten. Deshalb unterscheidet sich ein eindimensionales Array von ganzen Zahlen von einem eindimensionalen Array von Double-Typen. In ähnlicher Weise unterscheidet sich ein zweidimensionales Array von ganzen Zahlen von einem eindimensionalen Array von ganzen Zahlen. Die Grenzen des Arrays werden beim Vergleichen von Typen nicht berücksichtigt.  
  
 Wie die folgende Tabelle zeigt, muss jede Instanz eines verwalteten Arrays über einen bestimmter Elementtyp, Rang und eine bestimmte Untergrenze verfügen.  
  
|Verwalteter Arraytyp|Elementtyp|Rang|Unterer Grenzwert|Signaturschreibweise|  
|------------------------|------------------|----------|-----------------|------------------------|  
|**ELEMENT_TYPE_ARRAY**|Durch den Typ angegeben.|Durch den Rang angegeben.|Optional durch Grenzen angegeben.|*Typ* **[** *n*,*m* **]**|  
|**ELEMENT_TYPE_CLASS**|Unbekannt|Unbekannt|Unbekannt|**System.Array**|  
|**ELEMENT_TYPE_SZARRAY**|Durch den Typ angegeben.|1|0|*Typ* **[** *n* **]**|  
  
## <a name="unmanaged-arrays"></a>Nicht verwaltete Arrays  

 Nicht verwaltete Arrays sind entweder sichere Arrays im COM-Stil oder Arrays im C-Stil mit fester oder variabler Länge. Sichere Arrays sind selbstbeschreibende Arrays, die den Typ, den Rang und die Grenzen der verknüpften Arraydaten enthalten. Arrays im C-Stil sind eindimensionale typisierte Arrays mit einer festen Untergrenze von 0. Der Marshallingdienst bietet nur eingeschränkt Unterstützung für beide Typen von Arrays.  
  
## <a name="passing-array-parameters-to-net-code"></a>Übergeben von Arrayparametern an .NET-Code  

 Arrays im C-Stil und sichere Arrays, können aus nicht verwaltetem Code an .NET-Code, als ein sicheres Array oder ein Array im C-Stil übergeben werden. Die folgende Tabelle zeigt den nicht verwalteten Typwert und den importierten Typ.  
  
|Nicht verwalteter Typ|Importierter Typ|  
|--------------------|-------------------|  
|**SafeArray(** *Typ* **)**|**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**<br /><br /> Rang = 1, Untergrenze = 0. Die Größe ist nur bekannt, wenn sie in der verwalteten Signatur bereitgestellt wird. Sichere Arrays, bei denen Rang = 1 oder Untergrenze = 0 nicht gilt, können nicht als **SZARRAY** gemarshallt werden.|  
|*Typ* **[]**|**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**<br /><br /> Rang = 1, Untergrenze = 0. Die Größe ist nur bekannt, wenn sie in der verwalteten Signatur bereitgestellt wird.|  
  
### <a name="safe-arrays"></a>Sichere Arrays  

 Wenn ein sicheres Array aus einer Typbibliothek in eine .NET-Assembly importiert wird, wird das Array in ein eindimensionales Array eines bekannten Typs konvertiert (z.B. **int**). Dieselben Typkonvertierungsregeln, die für Parameter gelten, gelten auch für Arrayelemente. So wird beispielsweise ein sicheres Array von **BSTR**-Typen zu einem verwalteten Array von Zeichenfolgen, und ein sicheres Array von Varianten zu einem verwalteten Array von Objekten. Der **SAFEARRAY**-Elementtyp wird aus der Typbibliothek abgerufen, und im **SAFEARRAY**-Wert der <xref:System.Runtime.InteropServices.UnmanagedType>-Enumeration gespeichert.  
  
 Da Rang und Grenzen eines sicheren Arrays über die Typbibliothek nicht bestimmt werden können, wird für den Rang ein Wert von 1 und für die Untergrenze ein Wert von 0 angenommen. Rang und Grenzen müssen in der vom [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) (Typbibliothek Importer) erzeugten verwalteten Signatur definiert werden. Wenn der zur Laufzeit an die Methode übergebene Rang unterschiedlich ist, wird eine <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> ausgelöst. Wenn der zur Laufzeit übergebene Arraytyp unterschiedlich ist, wird eine <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> ausgelöst. Das folgende Beispiel zeigt sichere Arrays in verwaltetem und nicht verwaltetem Code.  
  
 **Nicht verwaltete Signatur**  
  
```cpp
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 **Verwaltete Signatur**  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_I4)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_DATE)> _
   ar() As DateTime)  
Sub New3(ByRef <MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_BSTR)> _
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_I4)] int[] ar) ;  
void New2([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_DATE)]
   DateTime[] ar);  
void New3([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_BSTR)]
   ref String[] ar);  
```  
  
 Mehrdimensionale oder gebundene sichere Arrays mit einem Wert ungleich null, können in verwalteten Code gemarshallt werden, wenn die von Tlbimp.exe erzeugte Methodensignatur so geändert wird, dass sie einen Elementtyp von **ELEMENT_TYPE_ARRAY** anstelle von **ELEMENT_TYPE_SZARRAY** angibt. Alternativ können Sie den **/sysarray** -Schalter mit Tlbimp.exe verwenden, um alle Arrays als <xref:System.Array?displayProperty=nameWithType>-Objekte zu importieren. Wenn bekannt ist, dass das übergebene Array mehrdimensional ist, können Sie den durch Tlbimp.exeMicrosoft erzeugten Intermediate Language-Code (MSIL) bearbeiten, und diesen anschließend neu kompilieren. Ausführliche Informationen zum Ändern des MSIL-Codes finden Sie unter [Customizing Runtime Callable Wrappers (Anpassen von durch die Laufzeit aufrufbaren Wrappern)](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).  
  
### <a name="c-style-arrays"></a>Arrays im C-Stil  

 Wenn ein Array im C-Stil aus einer Typbibliothek in eine .NET Framework-Assembly importiert wird, wird das Array in **ELEMENT_TYPE_SZARRAY** konvertiert.  
  
 Der Elementtyp des Arrays wird durch die Typbibliothek bestimmt und während des Imports beibehalten. Dieselben Konvertierungsregeln, die für Parameter gelten, gelten auch für Arrayelemente. Ein Array von **LPStr**-Typen wird z.B. zu einem Array von **Zeichenfolge**-Typen. Tlbimp.exe erfasst den Elementtyp des Arrays und wendet das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut auf den Parameter an.  
  
 Es wird angenommen, dass der Rang des Arrays gleich 1 ist. Wenn der Rang größer als 1 ist, wird das Array als eindimensionales Array nach Spaltengröße gemarshallt. Die Untergrenze ist immer gleich 0.  
  
 Typbibliotheken können Arrays mit fester oder variabler Länge enthalten. Tlbimp.exe kann nur Arrays mit fester Länge aus Typbibliotheken importieren, da Typbibliotheken nicht die benötigten Informationen zum Marshallen von Arrays mit variabler Länge enthalten. Bei Arrays mit fester Länge, wird die Größe aus der Typbibliothek importiert und im **MarshalAsAttribute**, das auf den Parameter angewendet wird, erfasst.  
  
 Typbibliotheken, die Arrays mit variabler Länge beinhalten müssen, wie in folgendem Beispiel gezeigt, manuell definiert werden.  
  
 **Nicht verwaltete Signatur**  
  
```cpp
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 **Verwaltete Signatur**  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.LPArray, SizeConst=10)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, SizeConst=200)> _  
   ar() As Double)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)> _  
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.LPArray, SizeConst=10)] int[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray, SizeConst=200)] double[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray,
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)] String[] ar);  
```  
  
 Obwohl Sie das **Size_is**- oder **Length_is**-Attribut auf ein Array in der Interface Definition Language (IDL)-Quelle anwenden können, um einem Client die Größe mitzuteilen, übermittelt der Microsoft Interface Definition Language (MIDL)-Compiler diese Information nicht an die Typbibliothek. Ohne die Größe zu kennen, kann der Interop-Marshallingdienst die Arrayelemente nicht marshallen. Folglich werden Arrays mit variabler Länge als Verweisargumente importiert. Zum Beispiel:  
  
 **Nicht verwaltete Signatur**  
  
```cpp
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 **Verwaltete Signatur**  
  
```vb  
Sub New1(ByRef ar As Integer)  
Sub New2(ByRef ar As Double)  
Sub New3(ByRef ar As String)  
```  
  
```csharp  
void New1(ref int ar);
void New2(ref double ar);
void New3(ref String ar);
```  
  
 Sie können die Arraygröße für den Marshaller bereitstellen, indem Sie den durch Tlbimp.exe erzeugten Microsoft intermediate Language-Code (MSIL) bearbeiten und anschließend neu kompilieren. Ausführliche Informationen zum Ändern des MSIL-Codes finden Sie unter [Customizing Runtime Callable Wrappers (Anpassen von durch die Laufzeit aufrufbaren Wrappern)](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)). Um die Anzahl der Elemente im Array anzuzeigen, wenden Sie den <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Typ auf den Arrayparameter der verwalteten Methodendefinition durch eine der folgenden Vorgehensweisen an:  
  
- Geben Sie einen weiteren Parameter an, der die Anzahl der Elemente im Array enthält. Die Parameter werden anhand der Position bestimmt, beginnend mit dem ersten Parameter als Nummer 0.
  
    ```vb  
    Sub [New](ElemCnt As Integer, _  
       \<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       int ElemCnt,
       [MarshalAs(UnmanagedType.LPArray, SizeParamIndex=0)] int[] ar );  
    ```  
  
- Definieren Sie die Größe des Arrays als Konstante. Zum Beispiel:  
  
    ```vb  
    Sub [New](\<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 Beim Marshallen von Arrays aus nicht verwaltetem Code an verwalteten Code überprüft der Marshaller das dem Parameter zugeordnete **MarshalAsAttribute**, um die Arraygröße zu bestimmen. Wenn die Größe des Arrays nicht angegeben ist, wird nur ein Element gemarshallt.  
  
> [!NOTE]
> Das Attribut **MarshalAsAttribute** wirkt sich nicht auf das Marshallen verwalteter Arrays an nicht verwalteten Code aus. In dieser Richtung wird die Arraygröße durch Prüfung bestimmt. Es besteht keine Möglichkeit, einen Teil eines verwalteten Arrays zu marshallen.  
  
 Der Interop-Marshaller verwendet die **CoTaskMemAlloc**- und **CoTaskMemFree**-Methoden, um Speicherplatz zu belegen und abzurufen. Diese Methoden müssen auch bei der Speicherbelegung durch nicht verwalteten Code verwendet werden.  
  
## <a name="passing-arrays-to-com"></a>Übergeben von Arrays an COM  

 Alle verwalteten Arraytypen können von verwaltetem Code an nicht verwalteten Code übergeben werden. Abhängig vom verwalteten Typ und den auf diesen Typ angewendeten Attributen, kann, wie in der folgenden Tabelle gezeigt, das Array als sicheres Array oder als Array im C-Stil abgerufen werden.  
  
|Verwalteter Arraytyp|Exportiert als|  
|------------------------|-----------------|  
|**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**|<xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *Typ* **)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> Typ wird in der Signatur angegeben. Rang ist immer 1, Untergrenze ist immer 0. Die Größe ist immer zur Laufzeit bekannt.|  
|**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>** [ **\<** *bounds* **>** ]|**UnmanagedType.SafeArray(** *Typ* **)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> Typ, Rang und Grenzen sind in der Signatur angegeben. Die Größe ist immer zur Laufzeit bekannt.|  
|**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>**|**UT_Interface**<br /><br /> **UnmanagedType.SafeArray(** *Typ* **)**<br /><br /> Typ, Rang, Grenzen und Größe sind immer zur Laufzeit bekannt.|  
  
 In der OLE-Automatisierung, gibt es im Zusammenhang mit Arrays von Strukturen, die LPSTR oder LPWSTR enthalten eine Einschränkung.  Aus diesem Grund müssen **Zeichenfolge**-Felder als **UnmanagedType.BSTR** gemarshallt werden. Andernfalls wird eine Ausnahme ausgelöst.  
  
### <a name="element_type_szarray"></a>ELEMENT_TYPE_SZARRAY  

 Wenn eine Methode mit einem **ELEMENT_TYPE_SZARRAY**-Parameter (eindimensionales Array) aus einer .NET-Assembly in eine Typbibliothek exportiert wird, wird der Arrayparameter in ein **SAFEARRAY** eines gegebenen Typs konvertiert. Dieselben Konvertierungsregeln gelten für die Arrayelementtypen. Der Inhalt des verwalteten Arrays wird automatisch aus dem verwalteten Speicher in das **SAFEARRAY** kopiert. Zum Beispiel:  
  
#### <a name="managed-signature"></a>Verwaltete Signatur  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### <a name="unmanaged-signature"></a>Nicht verwaltete Signatur  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 Der Rang eines sicheren Arrays ist immer 1, und die Untergrenze ist immer 0. Die Größe wird zur Laufzeit durch die Größe des übergebenen verwalteten Arrays bestimmt.  
  
 Das Array kann auch als Array im C-Stil, mithilfe des <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attributs gemarshallt werden. Zum Beispiel:  
  
#### <a name="managed-signature"></a>Verwaltete Signatur  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As Long, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]
   long [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]
   String [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, ArraySubType=
   UnmanagedType.LPStr, SizeParamIndex=1)]
   String [] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a>Nicht verwaltete Signatur  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(BSTR ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 Obwohl der Marshaller die erforderlichen Längeninformationen zum Marshallen von Arrays hat, wird die Länge des Arrays in der Regel als separates Argument übergeben, um dem Aufgerufenen die Länge mitzuteilen.  
  
### <a name="element_type_array"></a>ELEMENT_TYPE_ARRAY  

 Wenn eine Methode mit einem **ELEMENT_TYPE_ARRAY**-Parameter aus einer .NET-Assembly in eine Typbibliothek exportiert wird, wird der Arrayparameter in ein **SAFEARRAY** eines gegebenen Typs konvertiert. Der Inhalt des verwalteten Arrays wird automatisch aus dem verwalteten Speicher in das **SAFEARRAY** kopiert. Zum Beispiel:  
  
#### <a name="managed-signature"></a>Verwaltete Signatur  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### <a name="unmanaged-signature"></a>Nicht verwaltete Signatur  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 Der Rang, die Größe und die Grenzen eines sicheren Arrays werden zur Laufzeit durch die Merkmale des verwalteten Arrays bestimmt.  
  
 Das Array kann auch als Array im C-Stil, mithilfe des <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attributs gemarshallt werden. Zum Beispiel:  
  
#### <a name="managed-signature"></a>Verwaltete Signatur  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex:=1)> _  
   ar(,) As Long, size As Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, _  
   ArraySubType:=UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar(,) As String, size As Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex=1)]
   long [,] ar, int size );  
void New([MarshalAs(UnmanagedType.LPARRAY,
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex=1)]
   String [,] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a>Nicht verwaltete Signatur  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 Geschachtelte Arrays können nicht gemarshallt werden. Die folgende Signatur generiert beispielsweise einen Fehler, wenn sie mit dem [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) exportiert wird.  
  
#### <a name="managed-signature"></a>Verwaltete Signatur  
  
```vb  
Sub [New](ar()()() As Long)  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### <a name="element_type_class-systemarray"></a>ELEMENT_TYPE_CLASS \<System.Array>  

 Wenn eine Methode, die einen <xref:System.Array?displayProperty=nameWithType>-Parameter enthält aus einer .NET-Assembly in eine Typbibliothek exportiert wird, wird der Arrayparameter in eine **_Array**-Schnittstelle konvertiert. Auf den Inhalt des verwalteten Arrays kann nur über die Methoden und Eigenschaften der **_Array**-Schnittstelle zugegriffen werden. **System.Array** kann auch als **SAFEARRAY**, mithilfe von <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attributen gemarshallt werden. Wenn die Arrayelemente als sicheres Array gemarshallt werden, werden sie als Varianten gemarshallt. Zum Beispiel:  
  
#### <a name="managed-signature"></a>Verwaltete Signatur  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### <a name="unmanaged-signature"></a>Nicht verwaltete Signatur  
  
```cpp
HRESULT New([in] _Array *ar);
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### <a name="arrays-within-structures"></a>Arrays in Strukturen  

 Nicht verwaltete Strukturen können eingebettete Arrays enthalten. Standardmäßig werden diese eingebetteten Arrayfelder als SAFEARRAY gemarshallt. Im folgenden Beispiel ist `s1` ein eingebettetes Array, das direkt innerhalb der Struktur selbst zugeordnet ist.  
  
#### <a name="unmanaged-representation"></a>Nicht verwalteten Darstellung  
  
```cpp
struct MyStruct {  
    short s1[128];  
}  
```  
  
 Arrays können als <xref:System.Runtime.InteropServices.UnmanagedType> gemarshallt sein, was das Einrichten des <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Felds voraussetzt. Die Größe kann nur als eine Konstante festgelegt werden. Der folgende Code zeigt die entsprechende verwaltete Definition von `MyStruct`.  
  
```vb  
Public Structure <StructLayout(LayoutKind.Sequential)> MyStruct  
   Public <MarshalAs(UnmanagedType.ByValArray, SizeConst := 128)> _  
     s1() As Short  
End Structure  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MyStruct {  
   [MarshalAs(UnmanagedType.ByValArray, SizeConst=128)] public short[] s1;  
}  
```  
  
## <a name="see-also"></a>Siehe auch

- [Default Marshaling Behavior (Standardmäßiges Marshallingverhalten)](default-marshaling-behavior.md)
- [Blitfähige und nicht blitfähige Typen](blittable-and-non-blittable-types.md)
- [Direktionale Attribute](/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))
- [Kopieren und Fixieren](copying-and-pinning.md)
