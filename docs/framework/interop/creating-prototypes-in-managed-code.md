---
title: Erstellen von Prototypen in verwaltetem Code
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
ms.openlocfilehash: 712040c3482b51c4dafe0ee87fdda8cd848fb7fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123620"
---
# <a name="creating-prototypes-in-managed-code"></a><span data-ttu-id="178cc-102">Erstellen von Prototypen in verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="178cc-102">Creating Prototypes in Managed Code</span></span>
<span data-ttu-id="178cc-103">In diesem Thema wird der Zugriff auf nicht verwaltete Funktionen beschrieben. Zudem werden verschiedene Attributfelder eingeführt, die die Methodendefinition in verwaltetem Code mit Anmerkungen versehen.</span><span class="sxs-lookup"><span data-stu-id="178cc-103">This topic describes how to access unmanaged functions and introduces several attribute fields that annotate method definition in managed code.</span></span> <span data-ttu-id="178cc-104">Beispiele für die Vorgehensweise beim Erstellen von .NET-basierten Deklarationen, die mit dem Plattformaufruf verwendet werden können, finden Sie unter [Marshaling Data with Platform Invoke (Marshallen von Daten mit Plattformaufruf)](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="178cc-104">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
 <span data-ttu-id="178cc-105">Bevor Sie auf eine nicht verwaltete DLL-Funktion in verwaltetem Code zugreifen können, müssen Sie den Namen der Funktion sowie den Namen der DLL kennen, die diese exportiert.</span><span class="sxs-lookup"><span data-stu-id="178cc-105">Before you can access an unmanaged DLL function from managed code, you need to know the name of the function and the name of the DLL that exports it.</span></span> <span data-ttu-id="178cc-106">Mit diesen Informationen können Sie damit beginnen, die verwaltete Definition für eine nicht verwaltete Funktion zu schreiben, die in einer DLL implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="178cc-106">With this information, you can begin to write the managed definition for an unmanaged function that is implemented in a DLL.</span></span> <span data-ttu-id="178cc-107">Darüber hinaus können Sie die Art und Weise anpassen, in der die Funktion durch Plattformaufrufe erstellt wird und die Daten zur und von der Funktion gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="178cc-107">Furthermore, you can adjust the way that platform invoke creates the function and marshals data to and from the function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="178cc-108">Mit Funktionen der Windows-API, die eine Zeichenfolge zuordnen, können Sie die Zeichenfolge mithilfe einer Methode wie z.B. `LocalFree` freigeben.</span><span class="sxs-lookup"><span data-stu-id="178cc-108">Windows API functions that allocate a string enable you to free the string by using a method such as `LocalFree`.</span></span> <span data-ttu-id="178cc-109">Der Plattformaufruf behandelt solche Parameter unterschiedlich auf andere Weise.</span><span class="sxs-lookup"><span data-stu-id="178cc-109">Platform invoke handles such parameters differently.</span></span> <span data-ttu-id="178cc-110">Für Plattformaufrufe verwenden Sie einen Parameter vom Typ `IntPtr` anstelle des Typs `String`.</span><span class="sxs-lookup"><span data-stu-id="178cc-110">For platform invoke calls, make the parameter an `IntPtr` type instead of a `String` type.</span></span> <span data-ttu-id="178cc-111">Verwenden Sie von der <xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>-Klasse bereitgestellte Methoden, um den Typ manuell in eine Zeichenfolge zu konvertieren und die Zeichenfolge dann manuell freizugeben.</span><span class="sxs-lookup"><span data-stu-id="178cc-111">Use methods that are provided by the <xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType> class to convert the type to a string manually and free it manually.</span></span>  
  
## <a name="declaration-basics"></a><span data-ttu-id="178cc-112">Grundlagen der Deklaration</span><span class="sxs-lookup"><span data-stu-id="178cc-112">Declaration Basics</span></span>  
 <span data-ttu-id="178cc-113">Verwaltete Definitionen für nicht verwaltete Funktionen hängen von der Sprache ab, wie Sie in den folgenden Beispielen erkennen können.</span><span class="sxs-lookup"><span data-stu-id="178cc-113">Managed definitions to unmanaged functions are language-dependent, as you can see in the following examples.</span></span> <span data-ttu-id="178cc-114">Ausführlichere Codebeispiele finden Sie unter [Beispiele für Plattformaufrufe](platform-invoke-examples.md).</span><span class="sxs-lookup"><span data-stu-id="178cc-114">For more complete code examples, see [Platform Invoke Examples](platform-invoke-examples.md).</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
 <span data-ttu-id="178cc-115">Um die Felder <xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError?displayProperty=nameWithType> oder <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar?displayProperty=nameWithType> auf eine Visual Basic-Deklaration anzuwenden, müssen Sie das <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut anstelle der `Declare`-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="178cc-115">To apply the <xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError?displayProperty=nameWithType>, or <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar?displayProperty=nameWithType> fields to a Visual Basic declaration, you must use the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute instead of the `Declare` statement.</span></span>  
  
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
  
## <a name="adjusting-the-definition"></a><span data-ttu-id="178cc-116">Anpassen der Definition</span><span class="sxs-lookup"><span data-stu-id="178cc-116">Adjusting the Definition</span></span>  
 <span data-ttu-id="178cc-117">Attributfelder müssen unabhängig davon, ob Sie sie explizit festlegen, das Verhalten von verwaltetem Code definieren.</span><span class="sxs-lookup"><span data-stu-id="178cc-117">Whether you set them explicitly or not, attribute fields are at work defining the behavior of managed code.</span></span> <span data-ttu-id="178cc-118">Der Plattformaufruf arbeitet gemäß den für verschiedene Felder festgelegten Standardwerten, die als Metadaten in einer Assembly vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="178cc-118">Platform invoke operates according to the default values set on various fields that exist as metadata in an assembly.</span></span> <span data-ttu-id="178cc-119">Sie können dieses Standardverhalten ändern, indem Sie die Werte von mindestens einem Feld anpassen.</span><span class="sxs-lookup"><span data-stu-id="178cc-119">You can alter this default behavior by adjusting the values of one or more fields.</span></span> <span data-ttu-id="178cc-120">In vielen Fällen verwenden Sie das <xref:System.Runtime.InteropServices.DllImportAttribute>, um einen Wert festzulegen.</span><span class="sxs-lookup"><span data-stu-id="178cc-120">In many cases, you use the <xref:System.Runtime.InteropServices.DllImportAttribute> to set a value.</span></span>  
  
 <span data-ttu-id="178cc-121">In der folgenden Tabelle ist der vollständige Satz an Attributfeldern aufgeführt, die den Plattformaufruf betreffen.</span><span class="sxs-lookup"><span data-stu-id="178cc-121">The following table lists the complete set of attribute fields that pertain to platform invoke.</span></span> <span data-ttu-id="178cc-122">Für jedes Feld enthält die Tabelle den Standardwert und einen Link zu Informationen darüber, wie diese Felder zum Definieren nicht verwalteter DLL-Funktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="178cc-122">For each field, the table includes the default value and a link to information on how to use these fields to define unmanaged DLL functions.</span></span>  
  
|<span data-ttu-id="178cc-123">Feld</span><span class="sxs-lookup"><span data-stu-id="178cc-123">Field</span></span>|<span data-ttu-id="178cc-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="178cc-124">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping>|<span data-ttu-id="178cc-125">Aktiviert oder deaktiviert die Zuordnung mit ähnlichen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="178cc-125">Enables or disables best-fit mapping.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention>|<span data-ttu-id="178cc-126">Gibt die Aufrufkonvention an, die bei der Übergabe von Methodenargumenten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="178cc-126">Specifies the calling convention to use in passing method arguments.</span></span> <span data-ttu-id="178cc-127">Der Standardwert ist `WinAPI`, was dem `__stdcall` für Intel-basierte 32-Bit-Plattformen entspricht.</span><span class="sxs-lookup"><span data-stu-id="178cc-127">The default is `WinAPI`, which corresponds to `__stdcall` for the 32-bit Intel-based platforms.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>|<span data-ttu-id="178cc-128">Die Namenszerlegung für Steuerelemente und die Art und Weise, in der Zeichenfolgenargumente an die Funktion gemarshallt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="178cc-128">Controls name mangling and the way that string arguments should be marshaled to the function.</span></span> <span data-ttu-id="178cc-129">Der Standardwert ist `CharSet.Ansi`.</span><span class="sxs-lookup"><span data-stu-id="178cc-129">The default is `CharSet.Ansi`.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>|<span data-ttu-id="178cc-130">Gibt den aufzurufenden DLL-Einstiegspunkt an.</span><span class="sxs-lookup"><span data-stu-id="178cc-130">Specifies the DLL entry point to be called.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>|<span data-ttu-id="178cc-131">Kontrolliert, ob ein Einstiegspunkt geändert werden muss, um dem Zeichensatz zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="178cc-131">Controls whether an entry point should be modified to correspond to the character set.</span></span> <span data-ttu-id="178cc-132">Der Standardwert variiert je nach Programmiersprache.</span><span class="sxs-lookup"><span data-stu-id="178cc-132">The default value varies by programming language.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>|<span data-ttu-id="178cc-133">Kontrolliert, ob die verwaltete Methodensignatur in eine nicht verwaltete Signatur transformiert werden soll, die ein HRESULT zurückgibt und über ein zusätzliches [out, retval]-Argument für den Rückgabewert verfügt.</span><span class="sxs-lookup"><span data-stu-id="178cc-133">Controls whether the managed method signature should be transformed into an unmanaged signature that returns an HRESULT and has an additional [out, retval] argument for the return value.</span></span><br /><br /> <span data-ttu-id="178cc-134">Der Standardwert ist `true` (die Signatur wird nicht transformiert).</span><span class="sxs-lookup"><span data-stu-id="178cc-134">The default is `true` (the signature should not be transformed).</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError>|<span data-ttu-id="178cc-135">Ermöglicht dem Aufrufer die Verwendung der `Marshal.GetLastWin32Error`-API-Funktion zur Ermittlung, ob beim Ausführen der Methode ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="178cc-135">Enables the caller to use the `Marshal.GetLastWin32Error` API function to determine whether an error occurred while executing the method.</span></span> <span data-ttu-id="178cc-136">In Visual Basic ist der Standardwert `true` In C# und C++ ist der Standardwert `false`.</span><span class="sxs-lookup"><span data-stu-id="178cc-136">In Visual Basic, the default is `true`; in C# and C++, the default is `false`.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar>|<span data-ttu-id="178cc-137">Steuert das Auslösen einer Ausnahme bei einem nicht zuzuordnenden Unicode-Zeichen, das in ein ANSI-Zeichen ("?") konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="178cc-137">Controls throwing of an exception on an unmappable Unicode character that is converted to an ANSI "?" character.</span></span>|  
  
 <span data-ttu-id="178cc-138">Detaillierte Verweisinformationen finden Sie unter <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="178cc-138">For detailed reference information, see <xref:System.Runtime.InteropServices.DllImportAttribute>.</span></span>  
  
## <a name="platform-invoke-security-considerations"></a><span data-ttu-id="178cc-139">Überlegungen zur Plattformaufrufsicherheit</span><span class="sxs-lookup"><span data-stu-id="178cc-139">Platform invoke security considerations</span></span>  
 <span data-ttu-id="178cc-140">Die Member `Assert`, `Deny` und `PermitOnly` der <xref:System.Security.Permissions.SecurityAction>-Enumeration werden als *stack walk modifier* (Stackwalkmodifizierer) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="178cc-140">The `Assert`, `Deny`, and `PermitOnly` members of the <xref:System.Security.Permissions.SecurityAction> enumeration are referred to as *stack walk modifiers*.</span></span> <span data-ttu-id="178cc-141">Diese Member werden ignoriert, wenn sie als deklarative Attribute für Deklarationen von Plattformaufrufen und COM-IDL-Anweisungen (Interface Definition Language) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="178cc-141">These members are ignored if they are used as declarative attributes on platform invoke declarations and COM Interface Definition Language (IDL) statements.</span></span>  
  
### <a name="platform-invoke-examples"></a><span data-ttu-id="178cc-142">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="178cc-142">Platform Invoke Examples</span></span>  
 <span data-ttu-id="178cc-143">Die Beispiele zum Plattformaufruf in diesem Abschnitt veranschaulichen die Verwendung des `RegistryPermission`-Attributs mit den Stapelmodifizierern.</span><span class="sxs-lookup"><span data-stu-id="178cc-143">The platform invoke samples in this section illustrate the use of the `RegistryPermission` attribute with the stack walk modifiers.</span></span>  
  
 <span data-ttu-id="178cc-144">Im folgenden Beispiel werden die Modifizierer <xref:System.Security.Permissions.SecurityAction>,`Assert`, `Deny` und `PermitOnly` ignoriert.</span><span class="sxs-lookup"><span data-stu-id="178cc-144">In the following example, the <xref:System.Security.Permissions.SecurityAction>`Assert`, `Deny`, and `PermitOnly` modifiers are ignored.</span></span>  
  
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
  
 <span data-ttu-id="178cc-145">Der `Demand`-Modifizierer im folgenden Beispiel wird jedoch akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="178cc-145">However, the `Demand` modifier in the following example is accepted.</span></span>  
  
```csharp
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 <span data-ttu-id="178cc-146"><xref:System.Security.Permissions.SecurityAction>-Modifizierer funktionieren ordnungsgemäß, wenn sie in einer Klasse positioniert werden, die den Plattformaufruf enthält (umschließt).</span><span class="sxs-lookup"><span data-stu-id="178cc-146"><xref:System.Security.Permissions.SecurityAction> modifiers do work correctly if they are placed on a class that contains (wraps) the platform invoke call.</span></span>  
  
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
  
 <span data-ttu-id="178cc-147"><xref:System.Security.Permissions.SecurityAction>-Modifizierer funktionieren auch in einem geschachtelten Szenario ordnungsgemäß, in dem sie im Aufrufer des Plattformaufrufs positioniert werden:</span><span class="sxs-lookup"><span data-stu-id="178cc-147"><xref:System.Security.Permissions.SecurityAction> modifiers also work correctly in a nested scenario where they are placed on the caller of the platform invoke call:</span></span>  
  
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
  
#### <a name="com-interop-examples"></a><span data-ttu-id="178cc-148">Beispiele zu COM-Interop</span><span class="sxs-lookup"><span data-stu-id="178cc-148">COM Interop Examples</span></span>  
 <span data-ttu-id="178cc-149">Die Beispiele zu COM-Interop in diesem Abschnitt veranschaulichen die Verwendung des `RegistryPermission`-Attributs mit den Stapelmodifizierern.</span><span class="sxs-lookup"><span data-stu-id="178cc-149">The COM interop samples in this section illustrate the use of the `RegistryPermission` attribute with the stack walk modifiers.</span></span>  
  
 <span data-ttu-id="178cc-150">Die folgenden Deklarationen der COM-Interop-Schnittstelle ignorieren die Modifizierer `Assert`, `Deny` und `PermitOnly` auf ähnliche Weise wie die Beispiele zum Plattformaufruf im vorherigen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="178cc-150">The following COM interop interface declarations ignore the `Assert`, `Deny`, and `PermitOnly` modifiers, similarly to the platform invoke examples in the previous section.</span></span>  
  
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
  
 <span data-ttu-id="178cc-151">Darüber hinaus wird der `Demand`-Modifizierer nicht in Deklarationsszenarien der COM-Interop-Schnittstelle akzeptiert, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="178cc-151">Additionally, the `Demand` modifier is not accepted in COM interop interface declaration scenarios, as shown in the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="178cc-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="178cc-152">See also</span></span>

- [<span data-ttu-id="178cc-153">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="178cc-153">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)
- [<span data-ttu-id="178cc-154">Angeben eines Einstiegspunktes</span><span class="sxs-lookup"><span data-stu-id="178cc-154">Specifying an Entry Point</span></span>](specifying-an-entry-point.md)
- [<span data-ttu-id="178cc-155">Festlegen eines Zeichensatzes</span><span class="sxs-lookup"><span data-stu-id="178cc-155">Specifying a Character Set</span></span>](specifying-a-character-set.md)
- [<span data-ttu-id="178cc-156">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="178cc-156">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- <span data-ttu-id="178cc-157">[Überlegungen zur Plattformaufrufsicherheit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb397754(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="178cc-157">[Platform Invoke Security Considerations](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb397754(v=vs.100))</span></span>
- [<span data-ttu-id="178cc-158">Identifizieren von Funktionen in DLLs</span><span class="sxs-lookup"><span data-stu-id="178cc-158">Identifying Functions in DLLs</span></span>](identifying-functions-in-dlls.md)
- [<span data-ttu-id="178cc-159">Erstellen einer Klasse zum Halten von DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="178cc-159">Creating a Class to Hold DLL Functions</span></span>](creating-a-class-to-hold-dll-functions.md)
- [<span data-ttu-id="178cc-160">Calling a DLL Function (Aufrufen einer DLL-Funktion)</span><span class="sxs-lookup"><span data-stu-id="178cc-160">Calling a DLL Function</span></span>](calling-a-dll-function.md)
