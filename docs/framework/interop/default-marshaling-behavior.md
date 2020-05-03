---
title: Standardmarshallingverhalten
ms.date: 06/26/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, default
- interoperation with unmanaged code, marshaling
- marshaling behavior
ms.assetid: c0a9bcdf-3df8-4db3-b1b6-abbdb2af809a
ms.openlocfilehash: f7df323dacfbee3361fe75d831f1e87df328b194
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989219"
---
# <a name="default-marshaling-behavior"></a>Standardmarshallingverhalten
Das Interop-Marshalling basiert auf Regeln, die vorgeben, wie sich Daten, die Methodenparametern zugeordnet sind, verhalten, wenn sie zwischen verwaltetem und unverwaltetem Speicher übergeben werden. Mit diesen integrierten Regeln werden Marshalling-Aktivitäten wie Datentyptransformationen gesteuert, es wird gesteuert, ob eine aufrufende Instanz die Daten ändern kann, die an sie übergeben werden, und ob diese Änderungen an den Aufrufer zurückgegeben werden, und unter welchen Umständen der Marshaller Leistungsoptimierungen bereitstellt.  
  
 Dieser Abschnitt befasst sich mit den standardmäßigen Verhaltensmerkmalen des Interop-Marshalling-Diensts. Er enthält detaillierte Informationen zum Marshallen von Arrays, booleschen Typen, Zeichentypen, Delegaten, Klassen, Objekten, Zeichenfolgen und Strukturen.  
  
> [!NOTE]
> Das Marshalling von generischen Typen wird nicht unterstützt. Weitere Informationen finden Sie unter [Interoperating Using Generic Types (Interoperation mit generischen Typen)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100)).  
  
## <a name="memory-management-with-the-interop-marshaler"></a>Speicherverwaltung mit dem Interop-Marshaller  
 Der Interop-Marshaller versucht immer, den von nicht verwaltetem Code belegten Speicher freizugeben. Dieses Verhalten entspricht den COM-Speicherverwaltungsregeln, unterscheidet sich jedoch von den Regeln, die für systemeigenes C++ gelten.  
  
 Es kann zu Missverständnissen kommen, wenn Sie das Verhalten von systemeigenem C++ (keine Speicherfreigabe) beim Plattformaufruf erwarten, bei dem automatisch Speicher für Zeiger freigegeben wird. Wenn Sie beispielsweise die folgende nicht verwaltete Methode aus einer C++-DLL aufrufen, wird kein Speicher automatisch freigegeben.  
  
### <a name="unmanaged-signature"></a>Nicht verwaltete Signatur  
  
```cpp  
BSTR MethodOne (BSTR b) {  
     return b;  
}  
```  
  
 Wenn Sie die Methode jedoch als einen Prototyp zum Plattformaufruf definieren, jeden **BSTR**-Typ durch einen <xref:System.String>-Typ ersetzen und `MethodOne` aufrufen, versucht die Common Language Runtime `b` zweimal freizugeben. Sie können das Marshalling-Verhalten ändern, indem Sie <xref:System.IntPtr>-Typen anstelle von **Zeichenfolgen**typen verwenden.  
  
 Zur Laufzeit wird immer die **CoTaskMemFree**-Methode zum Freigeben von Speicher verwendet. Wenn der Speicher, mit dem Sie arbeiten, nicht der **CoTaskMemAlloc**-Methode zugeordnet wurde, müssen Sie **IntPtr** verwenden und den Speicher manuell mit der geeigneten Methode freigeben. Ebenso können Sie in Situationen, in denen der Speicher niemals freigegeben werden soll, wie bei Verwendung der **GetCommandLine**-Funktion von Kernel32.dll, die einen Zeiger auf den Kernelspeicher zurückgibt, verhindern, dass Speicher automatisch freigegeben wird. Details zum manuellen Freigeben von Speicher finden Sie unter [Beispiel für Puffer](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x3txb6xc(v=vs.100)).  
  
## <a name="default-marshaling-for-classes"></a>Standardmäßiges Marshalling für Klassen  
 Klassen können nur durch COM-Interop gemarshallt werden und werden immer als Schnittstellen gemarshallt. In einigen Fällen wird die zum Marshallen der Klasse verwendete Schnittstelle als Klassenschnittstelle bezeichnet. Informationen zum Überschreiben der Klassenschnittstelle mit einer beliebigen Schnittstelle finden Sie unter [Einführung in die Klassenschnittstelle](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).  
  
### <a name="passing-classes-to-com"></a>Übergeben von Klassen an COM  
 Wenn eine verwaltete Klasse an COM übergeben wird, umschließt der Interop-Marshaller die Klasse automatisch mit einem COM-Proxy und übergibt die vom Proxy erstellte Klassenschnittstelle an den COM-Methodenaufruf. Der Proxy delegiert dann alle Aufrufe der Klassenschnittstelle zurück an das verwaltete Objekt. Der Proxy macht zudem auch weitere Schnittstellen verfügbar, die von der Klasse nicht explizit implementiert werden. Der Proxy implementiert automatisch Schnittstellen wie **IUnknown** und **IDispatch** für die Klasse.  
  
### <a name="passing-classes-to-net-code"></a>Übergeben von Klassen an .NET-Code  
 Co-Klassen werden in der Regel nicht als Methodenargumente in COM verwendet. Stattdessen wird normalerweise eine Standardschnittstelle anstelle der Co-Klasse übergeben.  
  
 Wenn eine Schnittstelle an verwalteten Code übergeben wird, ist der Interop-Marshaller für das Umschließen der Schnittstelle mit dem geeigneten Wrapper und das Übergeben des Wrappers an die verwaltete Methode zuständig. Herauszufinden, welcher Wrapper verwendet werden sollte, kann schwierig sein. Jede Instanz eines COM-Objekts verfügt über einen einzelnen, eindeutigen Wrapper, ganz gleich, wie viele Schnittstellen das Objekt implementiert. So hat ein einzelnes COM-Objekt, das fünf unterschiedliche Schnittstellen implementiert, nur einen einzigen Wrapper. Der gleiche Wrapper macht alle fünf Schnittstellen verfügbar. Wenn zwei Instanzen des COM-Objekts erstellt werden, werden auch zwei Instanzen des Wrappers erstellt.  
  
 Damit der Wrapper über die gesamte Lebensdauer den gleichen Typ beibehält, muss der Interop-Marshaller den korrekten Wrapper beim ersten Mal identifizieren, wenn ein vom Objekt verfügbar gemachte Schnittstelle über den Marshaller übergeben wird. Der Marshaller identifiziert das Objekt anhand einer der Schnittstellen, die von dem Objekt implementiert werden.  
  
 So bestimmt der Marshaller beispielsweise, dass der Klassenwrapper zum Umschließen der Schnittstelle verwendet werden soll, die an verwalteten Code übergeben wurde. Wenn die Schnittstelle erstmals über den Marshaller übergeben wird, prüft der Marshaller, ob die Schnittstelle von einem bekannten Objekt stammt. Diese Überprüfung erfolgt in zwei Situationen:  
  
- Eine Schnittstelle wird von einem anderen verwalteten Objekt implementiert, das an anderer Stelle an COM übergeben wurde. Der Marshaller kann die Schnittstellen, die von verwalteten Objekten verfügbar gemacht werden, leicht identifizieren und ist in der Lage, die Schnittstelle mit dem verwalteten Objekt zu vergleichen, das die Implementierung bereitstellt. Das verwaltete Objekt wird dann an die Methode übergeben, und es wird kein Wrapper benötigt.  
  
- Ein bereits umschlossenes Objekt implementiert die Schnittstelle. Um festzustellen, ob dies der Fall ist, fragt der Marshaller das Objekt nach seiner **IUnknown-Schnittstelle**, und vergleicht die zurückgegebene Schnittstelle mit den Schnittstellen von anderen Objekten, die bereits umschlossen sind. Wenn die Schnittstelle die gleiche wie die des anderen Wrappers ist, haben die Objekte die gleiche Identität, und der vorhandene Wrapper wird an die Methode übergeben.  
  
 Wenn die Schnittstelle nicht von einem bekannten Objekt stammt, geht der Marshaller folgendermaßen vor:  
  
1. Der Marshaller fragt das Objekt nach seiner **IProvideClassInfo2**-Schnittstelle ab. Wird diese zurückgegeben, verwendet der Marshaller die von **IProvideClassInfo2.GetGUID** zurückgegebene CLSID, um die Co-Klasse zu identifizieren, die die Schnittstelle bereitstellt. Mit der CLSID kann der Marshaller den Wrapper in der Registrierung finden, wenn die Assembly bereits registriert ist.  
  
2. Der Marshaller fragt die **IProvideClassInfo**-Schnittstelle der Schnittstelle ab. Wird diese zurückgegeben, verwendet der Marshaller die von **IProvideClassInfo.GetClassinfo** zurückgegebene **ITypeInfo**, um die CLSID der Klasse zu ermitteln, die die Schnittstelle verfügbar macht. Der Marshaller kann die CLSID verwenden, um die Metadaten für den Wrapper zu finden.  
  
3. Wenn der Marshaller die Klasse immer noch nicht identifizieren kann, umschließt er die Schnittstelle mit einer generischen Wrapperklasse mit Namen **System.__ComObject**.  
  
## <a name="default-marshaling-for-delegates"></a>Standardmäßiges Marshalling für Delegaten  
 Ein verwalteter Delegat wird als COM-Schnittstelle oder als Funktionszeiger gemarshallt, und zwar basierend auf dem Aufrufmechanismus:  
  
- Für Plattformaufrufe wird ein Delegat standardmäßig als unverwalteter Funktionszeiger gemarshallt.  
  
- Für COM-Interop wird ein Delegat standardmäßig als COM-Schnittstelle vom Typ **_Delegate** gemarshallt. Die **_Delegate**-Schnittstelle ist in der Typbibliothek Mscorlib.tlb definiert und enthält die <xref:System.Delegate.DynamicInvoke%2A?displayProperty=nameWithType>-Methode, mit der Sie in der Lage sind, die Methode aufzurufen, auf die der Delegat verweist.  
  
 Die folgende Tabelle zeigt die Marshalling-Optionen für den Datentyp "Verwalteter Delegat". Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut stellt mehrere <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswerte zum Marshallen von Delegaten bereit.  
  
|Enumerationstyp|Beschreibung des nicht verwalteten Formats|  
|----------------------|-------------------------------------|  
|**UnmanagedType.FunctionPtr**|Ein nicht verwaltete Funktionszeiger.|  
|**UnmanagedType.Interface**|Eine Schnittstelle von Typ **_Delegate**, wie in Mscorlib.tlb definiert.|  
  
 Schauen Sie sich den folgenden Beispielcode an, in dem Methoden von `DelegateTestInterface` in eine COM-Typbibliothek exportiert werden. Beachten Sie, dass nur Delegaten, die mit dem Schlüsselwort **ref** (oder **ByRef**) gekennzeichnet sind, als In/Out-Parameter übergeben werden.  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public interface DelegateTest {  
void m1(Delegate d);  
void m2([MarshalAs(UnmanagedType.Interface)] Delegate d);
void m3([MarshalAs(UnmanagedType.Interface)] ref Delegate d);
void m4([MarshalAs(UnmanagedType.FunctionPtr)] Delegate d);
void m5([MarshalAs(UnmanagedType.FunctionPtr)] ref Delegate d);
}  
```  
  
### <a name="type-library-representation"></a>Darstellung der Typbibliothek  
  
```cpp  
importlib("mscorlib.tlb");  
interface DelegateTest : IDispatch {  
[id(…)] HRESULT m1([in] _Delegate* d);  
[id(…)] HRESULT m2([in] _Delegate* d);  
[id(…)] HRESULT m3([in, out] _Delegate** d);  
[id()] HRESULT m4([in] int d);  
[id()] HRESULT m5([in, out] int *d);  
   };  
```  
  
 Ein Funktionszeiger kann dereferenziert werden, wie jeder andere nicht verwaltete Funktionszeiger dereferenziert werden kann.  

In diesem Beispiel ist das Ergebnis ein `int`-Typ und ein Zeiger auf einen `int`-Typ, wenn zwei Delegaten als <xref:System.Runtime.InteropServices.UnmanagedType.FunctionPtr?displayProperty=nameWithType> gemarshallt werden. Da Delegattypen gemarshallt werden, stellt `int` hier einen Zeiger auf einen `void*`-Typ dar, der der Adresse des Delegaten im Arbeitsspeicher entspricht. Das Ergebnis bezieht sich also auf 32-Bit-Windows-Systeme, da `int` in diesem Fall die Größe des Funktionszeigers darstellt.

> [!NOTE]
> Ein Verweis auf den Funktionszeiger auf einen verwalteten Delegaten in nicht verwaltetem Code hindert die Common Language Runtime nicht daran, eine Garbage Collection für das verwaltete Objekt durchzuführen.  
  
 Der folgende Code ist beispielsweise falsch, da der Verweis auf das `cb`-Objekt, der an die `SetChangeHandler`-Methode übergeben wurde, `cb` nicht über die Lebensdauer der `Test`-Methode hinaus gültig hält. Nachdem die Garbage Collection des `cb`-Objekts erfolgt ist, ist der an `SetChangeHandler` übergebene Funktionszeiger nicht mehr gültig.  
  
```csharp  
public class ExternalAPI {  
   [DllImport("External.dll")]  
   public static extern void SetChangeHandler(  
      [MarshalAs(UnmanagedType.FunctionPtr)]ChangeDelegate d);  
}  
public delegate bool ChangeDelegate([MarshalAs(UnmanagedType.LPWStr) string S);  
public class CallBackClass {  
   public bool OnChange(string S){ return true;}  
}  
internal class DelegateTest {  
   public static void Test() {  
      CallBackClass cb = new CallBackClass();  
      // Caution: The following reference on the cb object does not keep the
      // object from being garbage collected after the Main method
      // executes.  
      ExternalAPI.SetChangeHandler(new ChangeDelegate(cb.OnChange));
   }  
}  
```  
  
 Um der unerwarteten Garbage Collection entgegenzuwirken, muss der Aufrufer sicherstellen, dass das `cb`-Objekt gültig bleibt, solange der nicht verwaltete Funktionszeiger verwendet wird. Optional können Sie dafür sorgen, dass der nicht verwaltete Code den verwalteten Code benachrichtigt, wenn der Funktionszeiger nicht mehr benötigt wird, wie das folgende Beispiel zeigt.  
  
```csharp  
internal class DelegateTest {  
   CallBackClass cb;  
   // Called before ever using the callback function.  
   public static void SetChangeHandler() {  
      cb = new CallBackClass();  
      ExternalAPI.SetChangeHandler(new ChangeDelegate(cb.OnChange));  
   }  
   // Called after using the callback function for the last time.  
   public static void RemoveChangeHandler() {  
      // The cb object can be collected now. The unmanaged code is
      // finished with the callback function.  
      cb = null;  
   }  
}  
```  
  
## <a name="default-marshaling-for-value-types"></a>Standardmäßiges Marshalling für Werttypen  
 Die meisten Werttypen, wie ganze Zahlen und Gleitkommazahlen, sind [blitfähig](blittable-and-non-blittable-types.md) und müssen nicht gemarshallt werden. Andere, [nicht blitfähige](blittable-and-non-blittable-types.md) Typen werden im verwalteten und im nicht verwalteten Speicher unterschiedlich dargestellt und müssen gemarshallt werden. Wieder andere Typen erfordern eine explizite, über die Grenzen der Interoperation hinausgehende Formatierung.  
  
 Dieser Abschnitt enthält Informationen zu den folgenden formatierten Werttypen:  
  
- [Im Plattformaufruf verwendete Werttypen](#value-types-used-in-platform-invoke)  
  
- [In COM-Interop verwendete Werttypen](#value-types-used-in-com-interop)  
  
 Neben einer Beschreibung formatierter Typen befasst sich dieses Thema mit [Systemwerttypen](#system-value-types), die ein ungewöhnliches Marshallingverhalten aufweisen.  
  
 Ein formatierter Typ ist ein komplexer Typ, der Informationen enthält, mit denen explizit das Layout seiner Member im Speicher gesteuert wird. Informationen zum Memberlayout werden mit dem <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut bereitgestellt. Das Layout kann einen der folgenden <xref:System.Runtime.InteropServices.LayoutKind>-Enumerationswerte aufweisen:  
  
- **LayoutKind.Auto**  
  
     Gibt an, dass die Common Language Runtime die Member dieses Typs aus Gründen der Effizienz frei neu anordnen kann. Wenn ein Werttyp allerdings an nicht verwalteten Code übergeben wird, ist das Layout der Member vorhersehbar. Der Versuch, eine solche Struktur automatisch zu marshallen, bewirkt eine Ausnahme.  
  
- **LayoutKind.Sequential**  
  
     Gibt an, dass die Member des Typs im nicht verwalteten Speicher in der gleichen Reihenfolge angeordnet werden sollen, in der sie in der Definition des verwalteten Typs erscheinen.  
  
- **LayoutKind.Explicit**  
  
     Gibt an, dass die Member entsprechend dem <xref:System.Runtime.InteropServices.FieldOffsetAttribute> angeordnet werden, das mit jedem Feld angegeben wird.  
  
### <a name="value-types-used-in-platform-invoke"></a>Im Plattformaufruf verwendete Werttypen  
 Im folgenden Beispiel stellen die Typen `Point` und `Rect` Memberlayoutinformationen mithilfe von **StructLayoutAttribute** bereit.  
  
```vb  
Imports System.Runtime.InteropServices  
<StructLayout(LayoutKind.Sequential)> Public Structure Point  
   Public x As Integer  
   Public y As Integer  
End Structure  
<StructLayout(LayoutKind.Explicit)> Public Structure Rect  
   <FieldOffset(0)> Public left As Integer  
   <FieldOffset(4)> Public top As Integer  
   <FieldOffset(8)> Public right As Integer  
   <FieldOffset(12)> Public bottom As Integer  
End Structure  
```  
  
```csharp  
using System.Runtime.InteropServices;  
[StructLayout(LayoutKind.Sequential)]  
public struct Point {  
   public int x;  
   public int y;  
}
  
[StructLayout(LayoutKind.Explicit)]  
public struct Rect {  
   [FieldOffset(0)] public int left;  
   [FieldOffset(4)] public int top;  
   [FieldOffset(8)] public int right;  
   [FieldOffset(12)] public int bottom;  
}  
```  
  
 Beim Marshallen an nicht verwalteten Code werden diese formatierten Typen als Strukturen im C-Stil gemarshallt. Dies bietet eine einfache Möglichkeit zum Aufrufen einer nicht verwalteten API, die über Strukturargumente verfügt. So können die Strukturen `POINT` und `RECT` beispielsweise folgendermaßen an die **PtInRect**-Funktion der Microsoft Windows-API übergeben werden:  
  
```cpp  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 Sie können Strukturen unter Verwendung der folgenden Definition des Plattformaufrufs übergeben:  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function PtInRect Lib "User32.dll" (
        ByRef r As Rect, p As Point) As Boolean
End Class
```
  
```csharp
internal static class NativeMethods
{
   [DllImport("User32.dll")]
   internal static extern bool PtInRect(ref Rect r, Point p);
}
```
  
 Der Werttyp `Rect` muss mit einem Verweis übergeben werden, da die nicht verwaltete API einen Zeiger auf ein `RECT` erwartet, der an die Funktion übergeben wird. Der Werttyp `Point` wird nach Wert übergeben, da die nicht verwaltete API erwartet, dass `POINT` im Stack übergeben wird. Dieser feine Unterschied ist sehr wichtig. Verweise werden als Zeiger an nicht verwalteten Code übergeben. Werte werden im Stack an nicht verwalteten Code übergeben.  
  
> [!NOTE]
> Wenn ein formatierter Typ als Struktur gemarshallt wird, kann nur auf die Felder im Typ zugegriffen werden. Wenn der Typ Methoden, Eigenschaften oder Ereignisse aufweist, kann auf diese vom nicht verwalteten Code nicht zugegriffen werden.  
  
 Klassen können ebenfalls an nicht verwalteten Code als Strukturen im C-Stil gemarshallt werden, vorausgesetzt, sie weisen ein festes Memberlayout auf. Die Memberlayoutinformationen für eine Klasse werden ebenfalls mit dem <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut bereitgestellt. Der Hauptunterschied zwischen Werttypen mit festen Layout und Klassen mit festem Layout ist die Art und Weise, wie diese an nicht verwalteten Code gemarshallt werden. Werttypen werden nach Wert (im Stack) übergeben, und dementsprechend werden Änderungen, die von der aufgerufenen Instanz an Membern dieses Typs vorgenommen werden, dem Aufrufer nicht angezeigt. Verweistypen werden als Verweis übergeben (ein Verweis auf den Typ wird in den Stack übergeben); dementsprechend werden alle Änderungen, die von der aufgerufenen Instanz an blitfähigen Membern des Typs vorgenommen werden, für den Aufrufer angezeigt.  
  
> [!NOTE]
> Wenn ein Verweistyp nicht blitfähige Typen als Member enthält, muss die Konvertierung zwei Mal erfolgen: Das erste Mal, wenn ein Argument an die nicht verwaltete Seite übergeben wird, zum zweiten Mal bei der Rückgabe aus dem Aufruf. Aufgrund dieses zusätzlichen Aufwands müssen In/Out-Parameter explizit auf ein Argument angewendet werden, wenn der Aufrufer Änderungen sehen möchte, die von der aufgerufenen Instanz vorgenommen wurden.  
  
 Im folgenden Beispiel hat die `SystemTime`-Klasse ein sequenzielles Memberlayout und kann an die **GetSystemTime**-Funktion der Windows-API übergeben werden.  
  
```vb  
<StructLayout(LayoutKind.Sequential)> Public Class SystemTime  
   Public wYear As System.UInt16  
   Public wMonth As System.UInt16  
   Public wDayOfWeek As System.UInt16  
   Public wDay As System.UInt16  
   Public wHour As System.UInt16  
   Public wMinute As System.UInt16  
   Public wSecond As System.UInt16  
   Public wMilliseconds As System.UInt16  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
   public class SystemTime {  
   public ushort wYear;
   public ushort wMonth;  
   public ushort wDayOfWeek;
   public ushort wDay;
   public ushort wHour;
   public ushort wMinute;
   public ushort wSecond;
   public ushort wMilliseconds;
}  
```  
  
 Die **GetSystemTime**-Funktion ist wie folgt definiert:  
  
```cpp  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 Die entsprechende Definition des Plattformaufrufs für **GetSystemTime** lautet wie folgt:  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Sub GetSystemTime Lib "Kernel32.dll" (
        ByVal sysTime As SystemTime)
End Class
```
  
```csharp
internal static class NativeMethods
{
   [DllImport("Kernel32.dll", CharSet = CharSet.Auto)]
   internal static extern void GetSystemTime(SystemTime st);
}
```
  
 Beachten Sie, dass das `SystemTime`-Argument nicht als Verweisargument typisiert ist, da `SystemTime` eine Klasse und kein Werttyp ist. Im Gegensatz zu Werttypen werden Klassen im durch Verweis übergeben.  
  
 Das folgende Codebeispiel zeigt eine andere `Point`-Klasse, die eine Methode mit Namen `SetXY` aufweist. Der der Typ über ein sequenzielles Layout verfügt, kann er an nicht verwalteten Code übergeben und als Struktur gemarshallt werden. Der `SetXY`-Member kann jedoch nicht von nicht verwaltetem Code aufgerufen werden, obwohl das Objekt durch Verweis übergeben wird.  
  
```vb  
<StructLayout(LayoutKind.Sequential)> Public Class Point  
   Private x, y As Integer  
   Public Sub SetXY(x As Integer, y As Integer)  
      Me.x = x  
      Me.y = y  
   End Sub  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public class Point {  
   int x, y;  
   public void SetXY(int x, int y){
      this.x = x;  
      this.y = y;  
   }  
}  
```  
  
### <a name="value-types-used-in-com-interop"></a>In COM-Interop verwendete Werttypen  
 Formatierte Typen können auch an COM-Interop-Methodenaufrufe übergeben werden. Tatsache ist, dass Werttypen automatisch in Strukturen konvertiert werden, wenn sie in eine Typbibliothek exportiert werden. Wie im folgenden Beispiel gezeigt, wird der `Point`-Werttyp zu einer Typdefinition (typedef) mit Namen `Point`. Alle Verweise auf den `Point`-Werttyp an anderer Stelle in der Typbibliothek werden durch die `Point`-Typdefinition ersetzt.  
  
 **Darstellung der Typbibliothek**  
  
```cpp  
typedef struct tagPoint {  
   int x;  
   int y;  
} Point;  
interface _Graphics {  
   …  
   HRESULT SetPoint ([in] Point p)  
   HRESULT SetPointRef ([in,out] Point *p)  
   HRESULT GetPoint ([out,retval] Point *p)  
}  
```  
  
 Die gleichen Regeln, die zum Marshallen von Werten und Verweisen an Plattformaufrufe gelten, gelten auch beim Marshallen über COM-Schnittstellen. Wenn eine Instanz des `Point`-Werttyps von .NET Framework an COM übergeben wird, wird der `Point` nach Wert übergeben. Wenn der `Point`-Werttyp durch Verweis übergeben wird, wird ein Zeiger auf den `Point` in den Stack übergeben. Der Interop-Marshaller unterstützt kein höheres Maß an Dereferenzierung (**Point** \*\*) in beide Richtungen.  
  
> [!NOTE]
> Strukturen, bei denen der <xref:System.Runtime.InteropServices.LayoutKind>-Enumerationswert auf **Explicit** (Explizit) festgelegt ist, können in COM-Interop nicht verwendet werden, da die exportierte Typbibliothek kein explizites Layout darstellen kann.  
  
### <a name="system-value-types"></a>Systemwerttypen  
 Der <xref:System>-Namespace enthält mehrere Werttypen, die für die geschaltete Form von primitiven Datentypen der Laufzeit stehen. Beispielsweise steht die Werttypstruktur <xref:System.Int32?displayProperty=nameWithType> für die geschachtelte Form von **ELEMENT_TYPE_I4**. Anstatt diese Typen als Strukturen zu marshallen, wie dies bei anderen formatierten Typen der Fall ist, marshallen Sie sie in der gleichen Weise wie die primitiven Datentypen, die sie schachteln. **System.Int32** wird daher als **ELEMENT_TYPE_I4** anstatt als eine Struktur gemarshallt, die ein einziges Mitglied vom Typ **long** enthält. Die folgende Tabelle enthält eine Liste der Werttypen im Namespace **System**, bei denen es sich um geschachtelte Darstellungen von primitiven Datentypen handelt.  
  
|Systemwerttyp|Elementtyp|  
|-----------------------|------------------|  
|<xref:System.Boolean?displayProperty=nameWithType>|**ELEMENT_TYPE_BOOLEAN**|  
|<xref:System.SByte?displayProperty=nameWithType>|**ELEMENT_TYPE_I1**|  
|<xref:System.Byte?displayProperty=nameWithType>|**ELEMENT_TYPE_UI1**|  
|<xref:System.Char?displayProperty=nameWithType>|**ELEMENT_TYPE_CHAR**|  
|<xref:System.Int16?displayProperty=nameWithType>|**ELEMENT_TYPE_I2**|  
|<xref:System.UInt16?displayProperty=nameWithType>|**ELEMENT_TYPE_U2**|  
|<xref:System.Int32?displayProperty=nameWithType>|**ELEMENT_TYPE_I4**|  
|<xref:System.UInt32?displayProperty=nameWithType>|**ELEMENT_TYPE_U4**|  
|<xref:System.Int64?displayProperty=nameWithType>|**ELEMENT_TYPE_I8**|  
|<xref:System.UInt64?displayProperty=nameWithType>|**ELEMENT_TYPE_U8**|  
|<xref:System.Single?displayProperty=nameWithType>|**ELEMENT_TYPE_R4**|  
|<xref:System.Double?displayProperty=nameWithType>|**ELEMENT_TYPE_R8**|  
|<xref:System.String?displayProperty=nameWithType>|**ELEMENT_TYPE_STRING**|  
|<xref:System.IntPtr?displayProperty=nameWithType>|**ELEMENT_TYPE_I**|  
|<xref:System.UIntPtr?displayProperty=nameWithType>|**ELEMENT_TYPE_U**|  
  
 Einige andere Werttypen im Namespace **System** werden anders verarbeitet. Da der nicht verwaltete Code bereits über gut eingeführte Formate für diese Typen verfügt, geht der Marshaller nach speziellen Regel beim Marshallen dieser Typen vor. Die folgende Tabelle führt die speziellen Werttypen im Namespace **System** sowie den nicht verwalteten Typ auf, an den sie gemarshallt werden.  
  
|Systemwerttyp|IDL-Typ|  
|-----------------------|--------------|  
|<xref:System.DateTime?displayProperty=nameWithType>|**DATE**|  
|<xref:System.Decimal?displayProperty=nameWithType>|**DECIMAL**|  
|<xref:System.Guid?displayProperty=nameWithType>|**GUID**|  
|<xref:System.Drawing.Color?displayProperty=nameWithType>|**OLE_COLOR**|  
  
 Der folgende Code zeigt die Definition der nicht verwalteten Typen **DATE**, **GUID**, **DECIMAL** und **OLE_COLOR** in der Stdole2-Typbibliothek.  
  
#### <a name="type-library-representation"></a>Darstellung der Typbibliothek  
  
```cpp  
typedef double DATE;  
typedef DWORD OLE_COLOR;  
  
typedef struct tagDEC {  
    USHORT    wReserved;  
    BYTE      scale;  
    BYTE      sign;  
    ULONG     Hi32;  
    ULONGLONG Lo64;  
} DECIMAL;  
  
typedef struct tagGUID {  
    DWORD Data1;  
    WORD  Data2;  
    WORD  Data3;  
    BYTE  Data4[ 8 ];  
} GUID;  
```  
  
 Der folgende Code zeigt die entsprechenden Definitionen in der verwalteten `IValueTypes`-Schnittstelle.  
  
```vb  
Public Interface IValueTypes  
   Sub M1(d As System.DateTime)  
   Sub M2(d As System.Guid)  
   Sub M3(d As System.Decimal)  
   Sub M4(d As System.Drawing.Color)  
End Interface  
```  
  
```csharp  
public interface IValueTypes {  
   void M1(System.DateTime d);  
   void M2(System.Guid d);  
   void M3(System.Decimal d);  
   void M4(System.Drawing.Color d);  
}  
```  
  
#### <a name="type-library-representation"></a>Darstellung der Typbibliothek  
  
```cpp  
[…]  
interface IValueTypes : IDispatch {  
   HRESULT M1([in] DATE d);  
   HRESULT M2([in] GUID d);  
   HRESULT M3([in] DECIMAL d);  
   HRESULT M4([in] OLE_COLOR d);  
};  
```  
  
## <a name="see-also"></a>Siehe auch

- [Blitfähige und nicht blitfähige Typen](blittable-and-non-blittable-types.md)
- [Kopieren und Fixieren](copying-and-pinning.md)
- [Standardmäßiges Marshalling für Arrays](default-marshaling-for-arrays.md)
- [Standardmäßiges Marshalling für Objekte](default-marshaling-for-objects.md)
- [Standardmäßiges Marshalling für Zeichenfolgen](default-marshaling-for-strings.md)
