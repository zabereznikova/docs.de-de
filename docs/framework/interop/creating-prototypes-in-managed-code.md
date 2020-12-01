---
title: Erstellen von Prototypen in verwaltetem Code
description: Erstellen Sie in verwaltetem .NET-Code Prototypen, damit Sie auf nicht verwaltete Funktionen zugreifen und Attributfelder verwenden können, die die Methodendefinition in verwaltetem Code mit Anmerkungen versehen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- prototypes in managed code
- COM interop, DLL functions
- unmanaged functions
- platform invoke, creating prototypes
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke, object fields
- DLL functions
- object fields in platform invoke
ms.assetid: ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d
ms.openlocfilehash: 4260bc8b3f9a2550faa28dd4d35842327b4e5935
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244105"
---
# <a name="creating-prototypes-in-managed-code"></a>Erstellen von Prototypen in verwaltetem Code

In diesem Thema wird der Zugriff auf nicht verwaltete Funktionen beschrieben. Zudem werden verschiedene Attributfelder eingeführt, die die Methodendefinition in verwaltetem Code mit Anmerkungen versehen. Beispiele für die Vorgehensweise beim Erstellen von .NET-basierten Deklarationen, die mit dem Plattformaufruf verwendet werden können, finden Sie unter [Marshaling Data with Platform Invoke (Marshallen von Daten mit Plattformaufruf)](marshaling-data-with-platform-invoke.md).  
  
 Bevor Sie auf eine nicht verwaltete DLL-Funktion in verwaltetem Code zugreifen können, müssen Sie den Namen der Funktion sowie den Namen der DLL kennen, die diese exportiert. Mit diesen Informationen können Sie damit beginnen, die verwaltete Definition für eine nicht verwaltete Funktion zu schreiben, die in einer DLL implementiert ist. Darüber hinaus können Sie die Art und Weise anpassen, in der die Funktion durch Plattformaufrufe erstellt wird und die Daten zur und von der Funktion gemarshallt werden.  
  
> [!NOTE]
> Mit Funktionen der Windows-API, die eine Zeichenfolge zuordnen, können Sie die Zeichenfolge mithilfe einer Methode wie z.B. `LocalFree` freigeben. Der Plattformaufruf behandelt solche Parameter unterschiedlich auf andere Weise. Für Plattformaufrufe verwenden Sie einen Parameter vom Typ `IntPtr` anstelle des Typs `String`. Verwenden Sie von der <xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>-Klasse bereitgestellte Methoden, um den Typ manuell in eine Zeichenfolge zu konvertieren und die Zeichenfolge dann manuell freizugeben.  
  
## <a name="declaration-basics"></a>Grundlagen der Deklaration  

 Verwaltete Definitionen für nicht verwaltete Funktionen hängen von der Sprache ab, wie Sie in den folgenden Beispielen erkennen können. Ausführlichere Codebeispiele finden Sie unter [Beispiele für Plattformaufrufe](platform-invoke-examples.md).  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
 Um die Felder <xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError?displayProperty=nameWithType> oder <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar?displayProperty=nameWithType> auf eine Visual Basic-Deklaration anzuwenden, müssen Sie das <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut anstelle der `Declare`-Anweisung verwenden.  
  
```vb
Imports System.Runtime.InteropServices

Friend Class NativeMethods
    <DllImport("user32.dll", CharSet:=CharSet.Auto)>
    Friend Shared Function MessageBox(
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
    End Function
End Class
```
  
```csharp
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
{
    [DllImport("user32.dll")]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```
  
```cpp
using namespace System;
using namespace System::Runtime::InteropServices;

[DllImport("user32.dll")]
extern "C" int MessageBox(
    IntPtr hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="adjusting-the-definition"></a>Anpassen der Definition  

 Attributfelder müssen unabhängig davon, ob Sie sie explizit festlegen, das Verhalten von verwaltetem Code definieren. Der Plattformaufruf arbeitet gemäß den für verschiedene Felder festgelegten Standardwerten, die als Metadaten in einer Assembly vorhanden sind. Sie können dieses Standardverhalten ändern, indem Sie die Werte von mindestens einem Feld anpassen. In vielen Fällen verwenden Sie das <xref:System.Runtime.InteropServices.DllImportAttribute>, um einen Wert festzulegen.  
  
 In der folgenden Tabelle ist der vollständige Satz an Attributfeldern aufgeführt, die den Plattformaufruf betreffen. Für jedes Feld enthält die Tabelle den Standardwert und einen Link zu Informationen darüber, wie diese Felder zum Definieren nicht verwalteter DLL-Funktionen verwendet werden.  
  
|Feld|Beschreibung|  
|-----------|-----------------|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping>|Aktiviert oder deaktiviert die Zuordnung mit ähnlichen Zeichen.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention>|Gibt die Aufrufkonvention an, die bei der Übergabe von Methodenargumenten verwendet wird. Der Standardwert ist `WinAPI`, was dem `__stdcall` für Intel-basierte 32-Bit-Plattformen entspricht.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>|Die Namenszerlegung für Steuerelemente und die Art und Weise, in der Zeichenfolgenargumente an die Funktion gemarshallt werden sollen. Der Standardwert ist `CharSet.Ansi`.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>|Gibt den aufzurufenden DLL-Einstiegspunkt an.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>|Kontrolliert, ob ein Einstiegspunkt geändert werden muss, um dem Zeichensatz zu entsprechen. Der Standardwert variiert je nach Programmiersprache.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>|Kontrolliert, ob die verwaltete Methodensignatur in eine nicht verwaltete Signatur transformiert werden soll, die ein HRESULT zurückgibt und über ein zusätzliches [out, retval]-Argument für den Rückgabewert verfügt.<br /><br /> Der Standardwert ist `true` (die Signatur wird nicht transformiert).|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError>|Ermöglicht dem Aufrufer die Verwendung der `Marshal.GetLastWin32Error`-API-Funktion zur Ermittlung, ob beim Ausführen der Methode ein Fehler aufgetreten ist. In Visual Basic ist der Standardwert `true` In C# und C++ ist der Standardwert `false`.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar>|Steuert das Auslösen einer Ausnahme bei einem nicht zuzuordnenden Unicode-Zeichen, das in ein ANSI-Zeichen ("?") konvertiert wird.|  
  
 Detaillierte Verweisinformationen finden Sie unter <xref:System.Runtime.InteropServices.DllImportAttribute>.  
  
## <a name="platform-invoke-security-considerations"></a>Überlegungen zur Plattformaufrufsicherheit  

 Die Member `Assert`, `Deny` und `PermitOnly` der <xref:System.Security.Permissions.SecurityAction>-Enumeration werden als *stack walk modifier* (Stackwalkmodifizierer) bezeichnet. Diese Member werden ignoriert, wenn sie als deklarative Attribute für Deklarationen von Plattformaufrufen und COM-IDL-Anweisungen (Interface Definition Language) verwendet werden.  
  
### <a name="platform-invoke-examples"></a>Beispiele für Plattformaufrufe  

 Die Beispiele zum Plattformaufruf in diesem Abschnitt veranschaulichen die Verwendung des `RegistryPermission`-Attributs mit den Stapelmodifizierern.  
  
 Im folgenden Beispiel werden die Modifizierer <xref:System.Security.Permissions.SecurityAction>,`Assert`, `Deny` und `PermitOnly` ignoriert.  
  
```csharp  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionAssert();  
  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Deny, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 Der `Demand`-Modifizierer im folgenden Beispiel wird jedoch akzeptiert.  
  
```csharp
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 <xref:System.Security.Permissions.SecurityAction>-Modifizierer funktionieren ordnungsgemäß, wenn sie in einer Klasse positioniert werden, die den Plattformaufruf enthält (umschließt).  
  
```cpp  
      [RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
public ref class PInvokeWrapper  
{  
public:  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
};  
```  
  
```csharp  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
class PInvokeWrapper  
{  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
}  
```  
  
 <xref:System.Security.Permissions.SecurityAction>-Modifizierer funktionieren auch in einem geschachtelten Szenario ordnungsgemäß, in dem sie im Aufrufer des Plattformaufrufs positioniert werden:  
  
```cpp  
      {  
public ref class PInvokeWrapper  
public:  
    [DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
  
    [RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    public static bool CallRegistryPermission()  
    {  
     return CallRegistryPermissionInternal();  
    }  
};  
```  
  
```csharp  
class PInvokeScenario  
{  
    [DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionInternal();  
  
    [RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    public static bool CallRegistryPermission()  
    {  
     return CallRegistryPermissionInternal();  
    }  
}  
```  
  
#### <a name="com-interop-examples"></a>Beispiele zu COM-Interop  

 Die Beispiele zu COM-Interop in diesem Abschnitt veranschaulichen die Verwendung des `RegistryPermission`-Attributs mit den Stapelmodifizierern.  
  
 Die folgenden Deklarationen der COM-Interop-Schnittstelle ignorieren die Modifizierer `Assert`, `Deny` und `PermitOnly` auf ähnliche Weise wie die Beispiele zum Plattformaufruf im vorherigen Abschnitt.  
  
```csharp
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IAssertStubsItf  
{  
[RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Assert, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IDenyStubsItf  
{  
[RegistryPermission(SecurityAction.Deny, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Deny, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IAssertStubsItf  
{  
[RegistryPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
```  
  
 Darüber hinaus wird der `Demand`-Modifizierer nicht in Deklarationsszenarien der COM-Interop-Schnittstelle akzeptiert, wie im folgenden Beispiel veranschaulicht.  
  
```csharp  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IDemandStubsItf  
{  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Demand, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
```  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden nicht verwalteter DLL-Funktionen](consuming-unmanaged-dll-functions.md)
- [Angeben eines Einstiegspunktes](specifying-an-entry-point.md)
- [Festlegen eines Zeichensatzes](specifying-a-character-set.md)
- [Beispiele für Plattformaufrufe](platform-invoke-examples.md)
- [Überlegungen zur Plattformaufrufsicherheit](/previous-versions/dotnet/netframework-4.0/bb397754(v=vs.100))
- [Identifizieren von Funktionen in DLLs](identifying-functions-in-dlls.md)
- [Erstellen einer Klasse zum Halten von DLL-Funktionen](creating-a-class-to-hold-dll-functions.md)
- [Calling a DLL Function (Aufrufen einer DLL-Funktion)](calling-a-dll-function.md)
