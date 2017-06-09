---
title: "Default Marshaling for Arrays | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "interop marshaling, arrays"
  - "arrays, interop marshaling"
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Default Marshaling for Arrays
In Anwendungen, die ausschließlich aus verwaltetem Code bestehen, übergibt die Common Language Runtime Arraytypen als In\/Out\-Parameter.  Der Interop\-Marshaller übergibt Arrays dagegen standardmäßig als In\-Parameter.  
  
 Bei Verwendung der [Fixierungsoptimierung](../../../docs/framework/interop/copying-and-pinning.md) kann ein blitfähiges Array beim Zusammenwirken mit Objekten in demselben Apartment den Anschein erwecken, dass es als In\/Out\-Parameter fungiert.  Wenn Sie den Code jedoch später in eine Typbibliothek exportieren, mit der der computerübergreifende Proxy generiert wird, und diese Bibliothek dazu verwendet wird, die apartmentübergreifenden Aufrufe zu marshallen, verhalten sich die Aufrufe möglicherweise wieder wie wirkliche In\-Parameter.  
  
 Arrays sind naturgemäß komplex, und die Unterschiede zwischen verwalteten und nicht verwalteten Arrays bieten mehr Informationen als andere nicht blitfähige Typen.  In diesem Thema erhalten Sie folgende Informationen zum Marshalling von Arrays:  
  
-   [Verwaltete Arrays](#cpcondefaultmarshalingforarraysanchor1)  
  
-   [Nicht verwaltete Arrays](#cpcondefaultmarshalingforarraysanchor2)  
  
-   [Übergeben von Arrayparametern an .NET\-Code](#cpcondefaultmarshalingforarraysanchor3)  
  
-   [Übergeben von Arrays an COM](#cpcondefaultmarshalingforarraysanchor4)  
  
<a name="cpcondefaultmarshalingforarraysanchor1"></a>   
## Verwaltete Arrays  
 Zwischen verwalteten Arraytypen können Unterschiede bestehen, die Basisklasse aller Arraytypen ist jedoch die <xref:System.Array?displayProperty=fullName>\-Klasse.  Die **System.Array**\-Klasse enthält Eigenschaften zur Bestimmung des Ranges, der Länge und der Ober\- und Untergrenze eines Arrays sowie Methoden zum Abrufen, Sortieren, Suchen, Kopieren und Erstellen von Arrays.  
  
 Diese Arraytypen sind dynamisch; für sie sind in der Basisklassenbibliothek keine entsprechenden statischen Typen vorhanden.  Sie können sich jede Kombination aus Elementtyp und Rang als einen gesonderten Arraytyp vorstellen.  Daher unterscheidet sich der Typ eines eindimensionalen Arrays von ganzen Zahlen von dem eines eindimensionalen Arrays von Double\-Typen.  In ähnlicher Weise unterscheidet sich ein zweidimensionales Array von ganzen Zahlen von einem eindimensionalen Array von ganzen Zahlen.  Beim Vergleichen von Typen werden die Grenzen des Arrays nicht berücksichtigt.  
  
 Wie die folgende Tabelle zeigt, muss jede Instanz eines verwalteten Arrays über einen bestimmten Elementtyp, Rang und eine bestimmte Untergrenze verfügen.  
  
|Verwalteter Arraytyp|Elementtyp|Rang|Unterer Grenzwert|Signaturschreibweise|  
|--------------------------|----------------|----------|-----------------------|--------------------------|  
|**ELEMENT\_TYPE\_ARRAY**|Durch den Typ angegeben.|Durch den Rang  angegeben.|Optional durch Grenzen  angegeben.|*Typ* **\[** *n*,*m* **\]**|  
|**ELEMENT\_TYPE\_CLASS**|Unbekannt|Unbekannt|Unbekannt|**System.Array**|  
|**ELEMENT\_TYPE\_SZARRAY**|Durch den Typ angegeben.|1|0|*Typ* **\[** *n* **\]**|  
  
<a name="cpcondefaultmarshalingforarraysanchor2"></a>   
## Nicht verwaltete Arrays  
 Nicht verwaltete Arrays sind sichere Arrays im COM\-Format oder Arrays mit fester oder variabler Länge im C\-Format.  Sichere Arrays sind selbstbeschreibende Arrays, die Typ, Rang und Grenzen der zugeordneten Arraydaten enthalten.  Arrays im C\-Format sind eindimensionale typisierte Arrays mit einer festen Untergrenze von 0.  Der Marshallingdienst unterstützt beide Typen von Arrays mit Einschränkungen.  
  
<a name="cpcondefaultmarshalingforarraysanchor3"></a>   
## Übergeben von Arrayparametern an .NET\-Code  
 Sowohl Arrays im C\-Format als auch sichere Arrays können als sichere Arrays oder Array im C\-Format aus nicht verwaltetem Code an .NET\-Code übergeben werden.  In der folgenden Tabelle sind der nicht verwaltete Typwert und der importierte Typ aufgelistet.  
  
|Nicht verwalteter Typ|Importierter Typ|  
|---------------------------|----------------------|  
|**SafeArray\(** *Typ* **\)**|**ELEMENT\_TYPE\_SZARRAY** **\<** *KonvertierterTyp* **\>**<br /><br /> Rang \= 1, Untergrenze \= 0.  Die Größe ist nur bekannt, wenn sie in der verwalteten Signatur bereitgestellt wird.  Sichere Arrays, bei denen Rang \= 1 oder Untergrenze \= 0 nicht gilt, können nicht als **SZARRAY** gemarshallt werden.|  
|*Typ*  **\[\]**|**ELEMENT\_TYPE\_SZARRAY** **\<** *KonvertierterTyp* **\>**<br /><br /> Rang \= 1, Untergrenze \= 0.  Die Größe ist nur bekannt, wenn sie in der verwalteten Signatur bereitgestellt wird.|  
  
### Sichere Arrays  
 Wenn ein sicheres Array aus einer Typbibliothek in eine .NET\-Assembly importiert wird, wird das Array in ein eindimensionales Array eines bekannten Typs \(z. B. **int**\) umgewandelt.  Für Arrayelemente gelten dieselben Typumwandlungsregeln wie für Parameter.  So wird ein sicheres Array von **BSTR**\-Typen beispielsweise in ein verwaltetes Array von Zeichenfolgen und ein sicheres Array von Varianten in ein verwaltetes Array von Objekten umgewandelt.  Der **SAFEARRAY**\-Elementtyp wird aus der Typbibliothek abgerufen und im **SAFEARRAY**\-Wert der <xref:System.Runtime.InteropServices.UnmanagedType>\-Enumeration gespeichert.  
  
 Da Rang und Grenzen des sicheren Arrays über die Typbibliothek nicht bestimmt werden können, wird für den Rang ein Wert von 1 und für die Untergrenze ein Wert von 0 angenommen.  Rang und Grenzen müssen in der vom [Type Library Importer \(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) erzeugten verwalteten Signatur definiert werden.  Wenn der zur Laufzeit an die Methode übergebene Rang sich von diesem Wert unterscheidet, wird eine <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> ausgelöst.  Wenn sich der zur Laufzeit übergebene Arraytyp von diesem Wert unterscheidet, wird eine <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> ausgelöst.  Im folgenden Beispiel werden sichere Arrays in verwaltetem und nicht verwaltetem Code gezeigt.  
  
 **Nicht verwaltete Signatur**  
  
```  
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
  
 Mehrdimensionale sichere Arrays oder sichere Arrays mit einem Grenzwert ungleich 0 können in verwalteten Code gemarshallt werden, wenn die durch Tlbimp.exe erstellte Methodensignatur so geändert wird, dass sie anstelle des Elementtyps **ELEMENT\_TYPE\_SZARRAY** den Elementtyp **ELEMENT\_TYPE\_ARRAY** angibt.  Alternativ dazu können Sie den **\/sysarray**\-Schalter mit Tlbimp.exe verwenden, um alle Arrays als <xref:System.Array?displayProperty=fullName>\-Objekte zu importieren.  Wenn bekannt ist, dass das zu übergebende Array mehrdimensional ist, können Sie den von Tlbimp.exe erzeugten MSIL\-Code \(Microsoft Intermediate Language\-Code\) bearbeiten und anschließend neu kompilieren.  Ausführliche Informationen zu Möglichkeiten, den MSIL\-Code zu ändern, finden Sie unter [Anpassen von durch die Laufzeit aufrufbaren Wrappern](http://msdn.microsoft.com/de-de/4652beaf-77d0-4f37-9687-ca193288c0be).  
  
### Arrays im C\-Format  
 Wenn ein Array im C\-Format aus einer Typbibliothek in eine .NET\-Assembly importiert wird, wird das Array in **ELEMENT\_TYPE\_SZARRAY** umgewandelt.  
  
 Der Elementtyp des Arrays wird durch die Typbibliothek bestimmt und während des Imports beibehalten.  Für Arrayelemente gelten dieselben Umwandlungsregeln wie für Parameter.  Ein Array von **LPStr**\-Typen wird beispielsweise in ein Array von **String**\-Typen umgewandelt.  Tlbimp.exe erfasst den Elementtyp des Arrays und wendet das <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Attribut auf den Parameter an.  
  
 Für den Rang des Arrays wird der Wert 1 angenommen.  Wenn der Rang größer als 1 ist, wird das Array als eindimensionales Array in der Reihenfolge der Spaltengröße gemarshallt.  Die Untergrenze ist immer gleich 0.  
  
 Typbibliotheken können Arrays fester oder variabler Länge enthalten.  Tlbimp.exe kann nur Arrays mit fester Länge aus Typbibliotheken importieren, weil Typbibliotheken nicht die zum Marshallen von Arrays mit variabler Länge erforderlichen Informationen enthalten.  Bei Arrays mit fester Länge wird die Größe aus der Typbibliothek importiert und im **MarshalAsAttribute**, das auf den Parameter angewendet wird, erfasst.  
  
 Typbibliotheken mit Arrays mit variabler Länge müssen manuell definiert werden \(siehe folgendes Beispiel\).  
  
 **Nicht verwaltete Signatur**  
  
```  
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
  
 Obwohl Sie das **size\_is**\-Attribut oder das **length\_is**\-Attribut auf ein Array in der Schnittstellendefinitionsquelle \(IDL, Interface Definition Language\) anwenden können, um einem Client die Größe mitzuteilen, überträgt der MIDL\-Compiler \(Microsoft Interface Definition Language\-Compiler\) diese Informationen nicht an die Typbibliothek.  Ohne die Größe zu kennen, kann der Interop\-Marshallingdienst die Arrayelemente nicht marshallen.  Infolgedessen werden Arrays variabler Länge als Verweisargumente importiert.  Beispiele:  
  
 **Nicht verwaltete Signatur**  
  
```  
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
  
 Sie können dem Marshaller die Arraygröße zur Verfügung stellen, indem Sie den durch Tlbimp.exe erzeugten MSIL\-Code \(Microsoft Intermediate Language\-Code\) bearbeiten und anschließend neu kompilieren.  Ausführliche Informationen zu Möglichkeiten, den MSIL\-Code zu ändern, finden Sie unter [Anpassen von durch die Laufzeit aufrufbaren Wrappern](http://msdn.microsoft.com/de-de/4652beaf-77d0-4f37-9687-ca193288c0be).  Um die Anzahl der Elemente im Array anzuzeigen, wenden Sie den <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Typ durch eine der folgenden Vorgehensweisen auf den Arrayparameter der verwalteten Methodendefinition an:  
  
-   Geben Sie einen weiteren Parameter an, der die Anzahl der Elemente im Array enthält.  Die Parameter werden durch die Position angegeben, beginnend mit dem ersten Parameter als 0.  \[Visual Basic\]  
  
    ```vb  
    Sub [New](ElemCnt As Integer, _  
       <MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
       ar() As Integer)  
  
    ```  
  
    ```csharp  
    void New(  
       int ElemCnt,   
       [MarshalAs(UnmanagedType.LPArray, SizeParamIndex=0)] int[] ar );  
    ```  
  
-   Definieren Sie die Arraygröße als Konstante.  Beispiele:  
  
    ```vb  
    Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 Wenn Arrays aus nicht verwaltetem an verwalteten Code gemarshallt werden, überprüft der Marshaller das dem Parameter zugeordnete **MarshalAsAttribute**, um die Arraygröße zu bestimmen.  Wenn die Arraygröße nicht angegeben ist, wird nur ein Element gemarshallt.  
  
> [!NOTE]
>  **MarshalAsAttribute** wirkt sich nicht auf das Marshallen verwalteter Arrays an nicht verwalteten Code aus.  In dieser Richtung wird die Arraygröße durch Untersuchung festgestellt.  Untergruppen verwalteter Arrays können nicht gemarshallt werden.  
  
 Um Speicherplatz zu belegen und abzurufen, verwendet der Interop\-Marshaller die **CoTaskMemAlloc**\-Methode und die **CoTaskMemFree**\-Methode.  Diese Methoden müssen auch bei der Speicherbelegung durch nicht verwalteten Code verwendet werden.  
  
<a name="cpcondefaultmarshalingforarraysanchor4"></a>   
## Übergeben von Arrays an COM  
 Alle verwalteten Arraytypen können von verwaltetem Code an nicht verwalteten Code übergeben werden.  In Abhängigkeit vom verwalteten Typ und den auf diesen Typ angewendeten Attributen kann das Array als sicheres Array oder als Array im C\-Format abgerufen werden \(siehe folgende Tabelle\).  
  
|Verwalteter Arraytyp|Exportiert als|  
|--------------------------|--------------------|  
|**ELEMENT\_TYPE\_SZARRAY** **\<** *Typ* **\>**|<xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray\(** *Typ* **\)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> Typ wird in der Signatur angegeben.  Der Rang ist immer 1, die Untergrenze ist immer 0.  Größe ist immer zur Laufzeit bekannt.|  
|**ELEMENT\_TYPE\_ARRAY** **\<** *Typ* **\>** **\<** *Rang* **\>**\[**\<** *Grenzen* **\>**\]|**UnmanagedType.SafeArray\(** *Typ* **\)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> Typ, Rang und Grenzen werden in der Signatur angegeben.  Größe ist immer zur Laufzeit bekannt.|  
|**ELEMENT\_TYPE\_CLASS** **\<**<xref:System.Array?displayProperty=fullName>**\>**|**UT\_Interface**<br /><br /> **UnmanagedType.SafeArray\(** *Typ* **\)**<br /><br /> Typ, Rang, Grenzen und Größe sind immer zur Laufzeit bekannt.|  
  
 In der OLE\-Automatisierung gibt es eine Einschränkung für Arrays von Strukturen, die LPSTR oder LPWSTR enthalten.  Deshalb müssen **String**\-Felder als **UnmanagedType.BSTR** gemarshallt werden.  Andernfalls wird eine Ausnahme ausgelöst.  
  
### ELEMENT\_TYPE\_SZARRAY  
 Wenn eine Methode mit einem **ELEMENT\_TYPE\_SZARRAY**\-Parameter \(eindimensionales Array\) aus einer .NET\-Assembly in eine Typbibliothek exportiert wird, wird der Arrayparameter in ein **SAFEARRAY** eines gegebenen Typs umgewandelt.  Für Arrayelementtypen gelten dieselben Umwandlungsregeln.  Der Inhalt des verwalteten Arrays wird automatisch aus dem verwalteten Speicher in das **SAFEARRAY** kopiert.  Beispiele:  
  
#### Verwaltete Signatur  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### Nicht verwaltete Signatur  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 Der Rang der sicheren Arrays ist immer 1, und die Untergrenze ist immer 0.  Die Größe wird zur Laufzeit anhand der Größe des verwalteten Arrays bestimmt, das übergeben wird.  
  
 Bei Verwendung des <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Attributs kann das Array auch als Array im C\-Format gemarshallt werden.  Beispiele:  
  
#### Verwaltete Signatur  
  
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
  
#### Nicht verwaltete Signatur  
  
```  
HRESULT New(long ar[]);   
HRESULT New(BSTR ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 Obwohl der Marshaller über die zum Marshallen des Arrays erforderlichen Längeninformationen verfügt, wird die Arraylänge normalerweise als separates Argument übergeben, um die Länge dem Aufgerufenen mitzuteilen.  
  
### ELEMENT\_TYPE\_ARRAY  
 Wenn eine Methode mit einem **ELEMENT\_TYPE\_ARRAY**\-Parameter aus einer .NET\-Assembly in eine Typbibliothek exportiert wird, wird der Arrayparameter in ein **SAFEARRAY** eines gegebenen Typs umgewandelt.  Der Inhalt des verwalteten Arrays wird automatisch aus dem verwalteten Speicher in das **SAFEARRAY** kopiert.  Beispiele:  
  
#### Verwaltete Signatur  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### Nicht verwaltete Signatur  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 Rang, Größe und Grenzen der sicheren Arrays werden zur Laufzeit anhand der Merkmale des verwalteten Arrays bestimmt.  
  
 Durch Anwenden des <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Attributs kann das Array auch als Array im C\-Format gemarshallt werden.  Beispiele:  
  
#### Verwaltete Signatur  
  
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
  
#### Nicht verwaltete Signatur  
  
```  
HRESULT New(long ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 Geschachtelte Arrays können nicht gemarshallt werden.  Die folgende Signatur generiert beispielsweise einen Fehler, wenn sie mit dem [Type Library Exporter\-Tool \(Tlbexp.exe\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) exportiert wird.  
  
#### Verwaltete Signatur  
  
```vb  
Sub [New](ar()()() As Long)  
  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### ELEMENT\_TYPE\_CLASS \<System.Array\>  
 Wenn eine Methode mit einem <xref:System.Array?displayProperty=fullName>\-Parameter aus einer .NET\-Assembly in eine Typbibliothek exportiert wird, wird der Arrayparameter in eine **\_Array**\-Schnittstelle umgewandelt.  Auf den Inhalt des verwalteten Arrays kann nur mit den Methoden und Eigenschaften der **\_Array**\-Schnittstelle zugegriffen werden.  **System.Array** kann auch als **SAFEARRAY** gemarshallt werden, indem das <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Attribut verwendet wird.  Wenn es als sicheres Array gemarshallt wird, werden die Arrayelemente als Varianten gemarshallt.  Beispiele:  
  
#### Verwaltete Signatur  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### Nicht verwaltete Signatur  
  
```  
HRESULT New([in] _Array *ar);   
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### Arrays in Strukturen  
 Nicht verwaltete Strukturen können eingebettete Arrays enthalten.  Standardmäßig werden diese eingebetteten Arrayfelder als SAFEARRAY gemarshallt.  Im folgenden Beispiel ist `s1` ein eingebettetes Array, das direkt innerhalb der Struktur selbst reserviert wird.  
  
#### Nicht verwaltete Repräsentation  
  
```  
struct MyStruct {  
    short s1[128];  
}  
```  
  
 Arrays können als [UnmanagedType.ByValArray](frlrfSystemRuntimeInteropServicesUnmanagedTypeClassTopic) gemarshallt werden. Dazu müssen Sie das [MarshalAsAttribute.SizeConst](frlrfSystemRuntimeInteropServicesMarshalAsAttributeClassTopic)\-Feld einrichten.  Die Größe kann nur als Konstante eingerichtet werden.  Im folgenden Code wird die entsprechende verwaltete Definition von  `MyStruct` demonstriert.  
  
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
  
## Siehe auch  
 [Default Marshaling Behavior](../../../docs/framework/interop/default-marshaling-behavior.md)   
 [Blittable and Non\-Blittable Types](../../../docs/framework/interop/blittable-and-non-blittable-types.md)   
 [Directional Attributes](http://msdn.microsoft.com/de-de/241ac5b5-928e-4969-8f58-1dbc048f9ea2)   
 [Copying and Pinning](../../../docs/framework/interop/copying-and-pinning.md)