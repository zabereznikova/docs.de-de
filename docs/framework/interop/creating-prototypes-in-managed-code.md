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
ms.openlocfilehash: 76b1a87c4513fdee21c5c3d5eba533b11e022e3a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622158"
---
# <a name="creating-prototypes-in-managed-code"></a><span data-ttu-id="9c0a5-103">Erstellen von Prototypen in verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="9c0a5-103">Creating Prototypes in Managed Code</span></span>
<span data-ttu-id="9c0a5-104">In diesem Thema wird der Zugriff auf nicht verwaltete Funktionen beschrieben. Zudem werden verschiedene Attributfelder eingeführt, die die Methodendefinition in verwaltetem Code mit Anmerkungen versehen.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-104">This topic describes how to access unmanaged functions and introduces several attribute fields that annotate method definition in managed code.</span></span> <span data-ttu-id="9c0a5-105">Beispiele für die Vorgehensweise beim Erstellen von .NET-basierten Deklarationen, die mit dem Plattformaufruf verwendet werden können, finden Sie unter [Marshaling Data with Platform Invoke (Marshallen von Daten mit Plattformaufruf)](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="9c0a5-105">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
 <span data-ttu-id="9c0a5-106">Bevor Sie auf eine nicht verwaltete DLL-Funktion in verwaltetem Code zugreifen können, müssen Sie den Namen der Funktion sowie den Namen der DLL kennen, die diese exportiert.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-106">Before you can access an unmanaged DLL function from managed code, you need to know the name of the function and the name of the DLL that exports it.</span></span> <span data-ttu-id="9c0a5-107">Mit diesen Informationen können Sie damit beginnen, die verwaltete Definition für eine nicht verwaltete Funktion zu schreiben, die in einer DLL implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-107">With this information, you can begin to write the managed definition for an unmanaged function that is implemented in a DLL.</span></span> <span data-ttu-id="9c0a5-108">Darüber hinaus können Sie die Art und Weise anpassen, in der die Funktion durch Plattformaufrufe erstellt wird und die Daten zur und von der Funktion gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-108">Furthermore, you can adjust the way that platform invoke creates the function and marshals data to and from the function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c0a5-109">Mit Funktionen der Windows-API, die eine Zeichenfolge zuordnen, können Sie die Zeichenfolge mithilfe einer Methode wie z.B. `LocalFree` freigeben.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-109">Windows API functions that allocate a string enable you to free the string by using a method such as `LocalFree`.</span></span> <span data-ttu-id="9c0a5-110">Der Plattformaufruf behandelt solche Parameter unterschiedlich auf andere Weise.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-110">Platform invoke handles such parameters differently.</span></span> <span data-ttu-id="9c0a5-111">Für Plattformaufrufe verwenden Sie einen Parameter vom Typ `IntPtr` anstelle des Typs `String`.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-111">For platform invoke calls, make the parameter an `IntPtr` type instead of a `String` type.</span></span> <span data-ttu-id="9c0a5-112">Verwenden Sie von der <xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>-Klasse bereitgestellte Methoden, um den Typ manuell in eine Zeichenfolge zu konvertieren und die Zeichenfolge dann manuell freizugeben.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-112">Use methods that are provided by the <xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType> class to convert the type to a string manually and free it manually.</span></span>  
  
## <a name="declaration-basics"></a><span data-ttu-id="9c0a5-113">Grundlagen der Deklaration</span><span class="sxs-lookup"><span data-stu-id="9c0a5-113">Declaration Basics</span></span>  
 <span data-ttu-id="9c0a5-114">Verwaltete Definitionen für nicht verwaltete Funktionen hängen von der Sprache ab, wie Sie in den folgenden Beispielen erkennen können.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-114">Managed definitions to unmanaged functions are language-dependent, as you can see in the following examples.</span></span> <span data-ttu-id="9c0a5-115">Ausführlichere Codebeispiele finden Sie unter [Beispiele für Plattformaufrufe](platform-invoke-examples.md).</span><span class="sxs-lookup"><span data-stu-id="9c0a5-115">For more complete code examples, see [Platform Invoke Examples](platform-invoke-examples.md).</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
 <span data-ttu-id="9c0a5-116">Um die Felder <xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError?displayProperty=nameWithType> oder <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar?displayProperty=nameWithType> auf eine Visual Basic-Deklaration anzuwenden, müssen Sie das <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut anstelle der `Declare`-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-116">To apply the <xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError?displayProperty=nameWithType>, or <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar?displayProperty=nameWithType> fields to a Visual Basic declaration, you must use the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute instead of the `Declare` statement.</span></span>  
  
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
  
## <a name="adjusting-the-definition"></a><span data-ttu-id="9c0a5-117">Anpassen der Definition</span><span class="sxs-lookup"><span data-stu-id="9c0a5-117">Adjusting the Definition</span></span>  
 <span data-ttu-id="9c0a5-118">Attributfelder müssen unabhängig davon, ob Sie sie explizit festlegen, das Verhalten von verwaltetem Code definieren.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-118">Whether you set them explicitly or not, attribute fields are at work defining the behavior of managed code.</span></span> <span data-ttu-id="9c0a5-119">Der Plattformaufruf arbeitet gemäß den für verschiedene Felder festgelegten Standardwerten, die als Metadaten in einer Assembly vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-119">Platform invoke operates according to the default values set on various fields that exist as metadata in an assembly.</span></span> <span data-ttu-id="9c0a5-120">Sie können dieses Standardverhalten ändern, indem Sie die Werte von mindestens einem Feld anpassen.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-120">You can alter this default behavior by adjusting the values of one or more fields.</span></span> <span data-ttu-id="9c0a5-121">In vielen Fällen verwenden Sie das <xref:System.Runtime.InteropServices.DllImportAttribute>, um einen Wert festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-121">In many cases, you use the <xref:System.Runtime.InteropServices.DllImportAttribute> to set a value.</span></span>  
  
 <span data-ttu-id="9c0a5-122">In der folgenden Tabelle ist der vollständige Satz an Attributfeldern aufgeführt, die den Plattformaufruf betreffen.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-122">The following table lists the complete set of attribute fields that pertain to platform invoke.</span></span> <span data-ttu-id="9c0a5-123">Für jedes Feld enthält die Tabelle den Standardwert und einen Link zu Informationen darüber, wie diese Felder zum Definieren nicht verwalteter DLL-Funktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-123">For each field, the table includes the default value and a link to information on how to use these fields to define unmanaged DLL functions.</span></span>  
  
|<span data-ttu-id="9c0a5-124">Feld</span><span class="sxs-lookup"><span data-stu-id="9c0a5-124">Field</span></span>|<span data-ttu-id="9c0a5-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c0a5-125">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping>|<span data-ttu-id="9c0a5-126">Aktiviert oder deaktiviert die Zuordnung mit ähnlichen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-126">Enables or disables best-fit mapping.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention>|<span data-ttu-id="9c0a5-127">Gibt die Aufrufkonvention an, die bei der Übergabe von Methodenargumenten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-127">Specifies the calling convention to use in passing method arguments.</span></span> <span data-ttu-id="9c0a5-128">Der Standardwert ist `WinAPI`, was dem `__stdcall` für Intel-basierte 32-Bit-Plattformen entspricht.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-128">The default is `WinAPI`, which corresponds to `__stdcall` for the 32-bit Intel-based platforms.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>|<span data-ttu-id="9c0a5-129">Die Namenszerlegung für Steuerelemente und die Art und Weise, in der Zeichenfolgenargumente an die Funktion gemarshallt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-129">Controls name mangling and the way that string arguments should be marshaled to the function.</span></span> <span data-ttu-id="9c0a5-130">Der Standardwert ist `CharSet.Ansi`.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-130">The default is `CharSet.Ansi`.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>|<span data-ttu-id="9c0a5-131">Gibt den aufzurufenden DLL-Einstiegspunkt an.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-131">Specifies the DLL entry point to be called.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>|<span data-ttu-id="9c0a5-132">Kontrolliert, ob ein Einstiegspunkt geändert werden muss, um dem Zeichensatz zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-132">Controls whether an entry point should be modified to correspond to the character set.</span></span> <span data-ttu-id="9c0a5-133">Der Standardwert variiert je nach Programmiersprache.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-133">The default value varies by programming language.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>|<span data-ttu-id="9c0a5-134">Kontrolliert, ob die verwaltete Methodensignatur in eine nicht verwaltete Signatur transformiert werden soll, die ein HRESULT zurückgibt und über ein zusätzliches [out, retval]-Argument für den Rückgabewert verfügt.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-134">Controls whether the managed method signature should be transformed into an unmanaged signature that returns an HRESULT and has an additional [out, retval] argument for the return value.</span></span><br /><br /> <span data-ttu-id="9c0a5-135">Der Standardwert ist `true` (die Signatur wird nicht transformiert).</span><span class="sxs-lookup"><span data-stu-id="9c0a5-135">The default is `true` (the signature should not be transformed).</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError>|<span data-ttu-id="9c0a5-136">Ermöglicht dem Aufrufer die Verwendung der `Marshal.GetLastWin32Error`-API-Funktion zur Ermittlung, ob beim Ausführen der Methode ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-136">Enables the caller to use the `Marshal.GetLastWin32Error` API function to determine whether an error occurred while executing the method.</span></span> <span data-ttu-id="9c0a5-137">In Visual Basic ist der Standardwert `true` In C# und C++ ist der Standardwert `false`.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-137">In Visual Basic, the default is `true`; in C# and C++, the default is `false`.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar>|<span data-ttu-id="9c0a5-138">Steuert das Auslösen einer Ausnahme bei einem nicht zuzuordnenden Unicode-Zeichen, das in ein ANSI-Zeichen ("?") konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-138">Controls throwing of an exception on an unmappable Unicode character that is converted to an ANSI "?" character.</span></span>|  
  
 <span data-ttu-id="9c0a5-139">Detaillierte Verweisinformationen finden Sie unter <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-139">For detailed reference information, see <xref:System.Runtime.InteropServices.DllImportAttribute>.</span></span>  
  
## <a name="platform-invoke-security-considerations"></a><span data-ttu-id="9c0a5-140">Überlegungen zur Plattformaufrufsicherheit</span><span class="sxs-lookup"><span data-stu-id="9c0a5-140">Platform invoke security considerations</span></span>  
 <span data-ttu-id="9c0a5-141">Die Member `Assert`, `Deny` und `PermitOnly` der <xref:System.Security.Permissions.SecurityAction>-Enumeration werden als *stack walk modifier* (Stackwalkmodifizierer) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-141">The `Assert`, `Deny`, and `PermitOnly` members of the <xref:System.Security.Permissions.SecurityAction> enumeration are referred to as *stack walk modifiers*.</span></span> <span data-ttu-id="9c0a5-142">Diese Member werden ignoriert, wenn sie als deklarative Attribute für Deklarationen von Plattformaufrufen und COM-IDL-Anweisungen (Interface Definition Language) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-142">These members are ignored if they are used as declarative attributes on platform invoke declarations and COM Interface Definition Language (IDL) statements.</span></span>  
  
### <a name="platform-invoke-examples"></a><span data-ttu-id="9c0a5-143">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="9c0a5-143">Platform Invoke Examples</span></span>  
 <span data-ttu-id="9c0a5-144">Die Beispiele zum Plattformaufruf in diesem Abschnitt veranschaulichen die Verwendung des `RegistryPermission`-Attributs mit den Stapelmodifizierern.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-144">The platform invoke samples in this section illustrate the use of the `RegistryPermission` attribute with the stack walk modifiers.</span></span>  
  
 <span data-ttu-id="9c0a5-145">Im folgenden Beispiel werden die Modifizierer <xref:System.Security.Permissions.SecurityAction>,`Assert`, `Deny` und `PermitOnly` ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-145">In the following example, the <xref:System.Security.Permissions.SecurityAction>`Assert`, `Deny`, and `PermitOnly` modifiers are ignored.</span></span>  
  
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
  
 <span data-ttu-id="9c0a5-146">Der `Demand`-Modifizierer im folgenden Beispiel wird jedoch akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-146">However, the `Demand` modifier in the following example is accepted.</span></span>  
  
```csharp
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 <span data-ttu-id="9c0a5-147"><xref:System.Security.Permissions.SecurityAction>-Modifizierer funktionieren ordnungsgemäß, wenn sie in einer Klasse positioniert werden, die den Plattformaufruf enthält (umschließt).</span><span class="sxs-lookup"><span data-stu-id="9c0a5-147"><xref:System.Security.Permissions.SecurityAction> modifiers do work correctly if they are placed on a class that contains (wraps) the platform invoke call.</span></span>  
  
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
  
 <span data-ttu-id="9c0a5-148"><xref:System.Security.Permissions.SecurityAction>-Modifizierer funktionieren auch in einem geschachtelten Szenario ordnungsgemäß, in dem sie im Aufrufer des Plattformaufrufs positioniert werden:</span><span class="sxs-lookup"><span data-stu-id="9c0a5-148"><xref:System.Security.Permissions.SecurityAction> modifiers also work correctly in a nested scenario where they are placed on the caller of the platform invoke call:</span></span>  
  
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
  
#### <a name="com-interop-examples"></a><span data-ttu-id="9c0a5-149">Beispiele zu COM-Interop</span><span class="sxs-lookup"><span data-stu-id="9c0a5-149">COM Interop Examples</span></span>  
 <span data-ttu-id="9c0a5-150">Die Beispiele zu COM-Interop in diesem Abschnitt veranschaulichen die Verwendung des `RegistryPermission`-Attributs mit den Stapelmodifizierern.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-150">The COM interop samples in this section illustrate the use of the `RegistryPermission` attribute with the stack walk modifiers.</span></span>  
  
 <span data-ttu-id="9c0a5-151">Die folgenden Deklarationen der COM-Interop-Schnittstelle ignorieren die Modifizierer `Assert`, `Deny` und `PermitOnly` auf ähnliche Weise wie die Beispiele zum Plattformaufruf im vorherigen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-151">The following COM interop interface declarations ignore the `Assert`, `Deny`, and `PermitOnly` modifiers, similarly to the platform invoke examples in the previous section.</span></span>  
  
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
  
 <span data-ttu-id="9c0a5-152">Darüber hinaus wird der `Demand`-Modifizierer nicht in Deklarationsszenarien der COM-Interop-Schnittstelle akzeptiert, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9c0a5-152">Additionally, the `Demand` modifier is not accepted in COM interop interface declaration scenarios, as shown in the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9c0a5-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c0a5-153">See also</span></span>

- [<span data-ttu-id="9c0a5-154">Verwenden nicht verwalteter DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="9c0a5-154">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)
- [<span data-ttu-id="9c0a5-155">Angeben eines Einstiegspunktes</span><span class="sxs-lookup"><span data-stu-id="9c0a5-155">Specifying an Entry Point</span></span>](specifying-an-entry-point.md)
- [<span data-ttu-id="9c0a5-156">Festlegen eines Zeichensatzes</span><span class="sxs-lookup"><span data-stu-id="9c0a5-156">Specifying a Character Set</span></span>](specifying-a-character-set.md)
- [<span data-ttu-id="9c0a5-157">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="9c0a5-157">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- <span data-ttu-id="9c0a5-158">[Überlegungen zur Plattformaufrufsicherheit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb397754(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9c0a5-158">[Platform Invoke Security Considerations](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb397754(v=vs.100))</span></span>
- [<span data-ttu-id="9c0a5-159">Identifizieren von Funktionen in DLLs</span><span class="sxs-lookup"><span data-stu-id="9c0a5-159">Identifying Functions in DLLs</span></span>](identifying-functions-in-dlls.md)
- [<span data-ttu-id="9c0a5-160">Erstellen einer Klasse zum Halten von DLL-Funktionen</span><span class="sxs-lookup"><span data-stu-id="9c0a5-160">Creating a Class to Hold DLL Functions</span></span>](creating-a-class-to-hold-dll-functions.md)
- [<span data-ttu-id="9c0a5-161">Calling a DLL Function (Aufrufen einer DLL-Funktion)</span><span class="sxs-lookup"><span data-stu-id="9c0a5-161">Calling a DLL Function</span></span>](calling-a-dll-function.md)
