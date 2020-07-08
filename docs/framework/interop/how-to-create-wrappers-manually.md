---
title: 'Vorgehensweise: Manuelles Erstellen von Wrappern'
description: Erfahren Sie, wie Sie Wrapper von COM-Typen manuell erstellen. Verwenden Sie eine vorhandene IDL-Datei oder Typbibliothek, oder erstellen Sie verwaltete Deklarationen, und exportieren Sie die Assembly in eine Typbibliothek.
ms.date: 03/30/2017
helpviewer_keywords:
- wrappers, creating manually
ms.assetid: cc2a70d8-6a58-4071-a8cf-ce28c018c09b
ms.openlocfilehash: e562a7e963ff744bf9193821d54dd898db521464
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619584"
---
# <a name="how-to-create-wrappers-manually"></a><span data-ttu-id="7143f-104">Vorgehensweise: Manuelles Erstellen von Wrappern</span><span class="sxs-lookup"><span data-stu-id="7143f-104">How to: Create Wrappers Manually</span></span>
<span data-ttu-id="7143f-105">Wenn Sie COM-Typen manuell in verwaltetem Quellcode deklarieren möchten, sollten Sie mit einer vorhandenen IDL-Datei oder -Typbibliothek (IDL, Interface Definition Language – Sprache für die Schnittstellendefinition) beginnen.</span><span class="sxs-lookup"><span data-stu-id="7143f-105">If you decide to declare COM types manually in managed source code, the best place to start is with an existing Interface Definition Language (IDL) file or type library.</span></span> <span data-ttu-id="7143f-106">Wenn Sie nicht über eine IDL-Datei verfügen oder keine Typbibliotheksdatei generieren können, können Sie die COM-Typen simulieren, indem Sie verwaltete Deklarationen erstellen und die sich daraus ergebende Assembly in eine Typbibliothek exportieren.</span><span class="sxs-lookup"><span data-stu-id="7143f-106">When you do not have the IDL file or cannot generate a type library file, you can simulate the COM types by creating managed declarations and exporting the resulting assembly to a type library.</span></span>  
  
### <a name="to-simulate-com-types-from-managed-source"></a><span data-ttu-id="7143f-107">So simulieren Sie COM-Typen aus verwaltetem Quellcode</span><span class="sxs-lookup"><span data-stu-id="7143f-107">To simulate COM types from managed source</span></span>  
  
1. <span data-ttu-id="7143f-108">Deklarieren Sie die Typen in einer Sprache, die mit der Common Language Specification (CLS) kompatibel ist, und kompilieren Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="7143f-108">Declare the types in a language that is compliant with the Common Language Specification (CLS) and compile the file.</span></span>  
  
2. <span data-ttu-id="7143f-109">Exportieren Sie die Assembly, die die Typen enthält, mit dem [Type Library Exporter-Tool (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="7143f-109">Export the assembly containing the types with the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
3. <span data-ttu-id="7143f-110">Verwenden Sie die exportierte COM-Typbibliothek als Grundlage zum Deklarieren der COM-orientierten verwalteten Typen.</span><span class="sxs-lookup"><span data-stu-id="7143f-110">Use the exported COM type library as a basis for declaring COM-oriented managed types.</span></span>  
  
### <a name="to-create-a-runtime-callable-wrapper-rcw"></a><span data-ttu-id="7143f-111">So erstellen Sie einen durch die Laufzeit aufrufbaren Wrapper (RCW, Runtime Callable Wrapper)</span><span class="sxs-lookup"><span data-stu-id="7143f-111">To create a runtime callable wrapper (RCW)</span></span>  
  
1. <span data-ttu-id="7143f-112">Wenn Sie über eine IDL-Datei oder eine Typbibliotheksdatei verfügen, legen Sie fest, welche Klassen und Schnittstellen Sie im benutzerdefinierten RCW einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="7143f-112">Assuming that you have an IDL file or type library file, decide which classes and interfaces you want to include in the custom RCW.</span></span> <span data-ttu-id="7143f-113">Sie können alle Typen ausschließen, die Sie nicht direkt oder indirekt in der Anwendung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7143f-113">You can exclude any types that you do not intend to use directly or indirectly in your application.</span></span>  
  
2. <span data-ttu-id="7143f-114">Erstellen Sie eine Quelldatei in einer CLS-kompatiblen Sprache, und deklarieren Sie die Typen.</span><span class="sxs-lookup"><span data-stu-id="7143f-114">Create a source file in a CLS-compliant language and declare the types.</span></span> <span data-ttu-id="7143f-115">Unter [Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100)) finden Sie eine vollständige Beschreibung des Importkonvertierungsprozesses.</span><span class="sxs-lookup"><span data-stu-id="7143f-115">See [Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100)) for a complete description of the import conversion process.</span></span> <span data-ttu-id="7143f-116">Wenn Sie also einen benutzerdefinierten RCW erstellen, führen Sie im Wesentlichen die durch das [Type Library Importer-Tool (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) bereitgestellte Typkonvertierungsaktivität manuell durch.</span><span class="sxs-lookup"><span data-stu-id="7143f-116">Effectively, when you create a custom RCW, you are manually performing the type conversion activity provided by the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="7143f-117">Das Beispiel im nächsten Abschnitt zeigt Typen in einer IDL- oder Typbibliotheksdatei sowie die zugehörigen Typen im C#-Code.</span><span class="sxs-lookup"><span data-stu-id="7143f-117">The example in the next section shows types in an IDL or type library file and their corresponding types in C# code.</span></span>  
  
3. <span data-ttu-id="7143f-118">Wenn die Deklarationen vollständig sind, kompilieren Sie die Datei so, wie Sie es für verwalteten Quellcode gewohnt sind.</span><span class="sxs-lookup"><span data-stu-id="7143f-118">When the declarations are complete, compile the file as you compile any other managed source code.</span></span>  
  
4. <span data-ttu-id="7143f-119">Analog zu den mit Tlbimp.exe importierten Typen benötigen einige Typen zusätzliche Informationen, die Sie dem Code direkt hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="7143f-119">As with the types imported with Tlbimp.exe, some require additional information, which you can add directly to your code.</span></span> <span data-ttu-id="7143f-120">Weitere Informationen finden Sie unter [Vorgehensweise: Bearbeiten von Interopassemblys](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="7143f-120">For details, see [How to: Edit Interop Assemblies](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7143f-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7143f-121">Example</span></span>  
 <span data-ttu-id="7143f-122">Im folgenden Code sind ein Beispiel der `ISATest`-Schnittstelle und der `SATest`-Klasse in IDL sowie die entsprechenden Typen im C#-Quellcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7143f-122">The following code shows an example of the `ISATest` interface and `SATest` class in IDL and the corresponding types in C# source code.</span></span>  
  
 <span data-ttu-id="7143f-123">**IDL-Datei oder -Typbibliotheksdatei**</span><span class="sxs-lookup"><span data-stu-id="7143f-123">**IDL or type library file**</span></span>  
  
```cpp
 [  
object,  
uuid(40A8C65D-2448-447A-B786-64682CBEF133),  
dual,  
helpstring("ISATest Interface"),  
pointer_default(unique)  
 ]  
interface ISATest : IDispatch  
 {  
[id(1), helpstring("method InSArray")]
HRESULT InSArray([in] SAFEARRAY(int) *ppsa, [out,retval] int *pSum);  
 };  
 [  
uuid(116CCA1E-7E39-4515-9849-90790DA6431E),  
helpstring("SATest Class")  
 ]  
coclass SATest  
 {  
  [default] interface ISATest;  
 };  
```  
  
 <span data-ttu-id="7143f-124">**Wrapper in verwaltetem Quellcode**</span><span class="sxs-lookup"><span data-stu-id="7143f-124">**Wrapper in managed source code**</span></span>  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
using System.Runtime.CompilerServices;  
  
[assembly:Guid("E4A992B8-6F5C-442C-96E7-C4778924C753")]  
[assembly:ImportedFromTypeLib("SAServerLib")]  
namespace SAServer  
{  
 [ComImport]  
 [Guid("40A8C65D-2448-447A-B786-64682CBEF133")]  
 [TypeLibType(TypeLibTypeFlags.FLicensed)]  
 public interface ISATest  
 {  
  [DispId(1)]  
  //[MethodImpl(MethodImplOptions.InternalCall,  
  // MethodCodeType=MethodCodeType.Runtime)]  
  int InSArray( [MarshalAs(UnmanagedType.SafeArray,  
      SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }
 [ComImport]  
 [Guid("116CCA1E-7E39-4515-9849-90790DA6431E")]  
 [ClassInterface(ClassInterfaceType.None)]  
 [TypeLibType(TypeLibTypeFlags.FCanCreate)]  
 public class SATest : ISATest  
 {  
  [DispId(1)]  
  [MethodImpl(MethodImplOptions.InternalCall,
  MethodCodeType=MethodCodeType.Runtime)]  
  extern int ISATest.InSArray( [MarshalAs(UnmanagedType.SafeArray,
  SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="7143f-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7143f-125">See also</span></span>

- <span data-ttu-id="7143f-126">[Anpassen von Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7143f-126">[Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span></span>
- <span data-ttu-id="7143f-127">[COM-Datentypen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7143f-127">[COM Data Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span></span>
- <span data-ttu-id="7143f-128">[How to: Bearbeiten von Interopassemblys](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7143f-128">[How to: Edit Interop Assemblies](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100))</span></span>
- <span data-ttu-id="7143f-129">[Zusammenfassung: Konvertieren einer Typbibliothek in eine Assembly](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7143f-129">[Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span></span>
- [<span data-ttu-id="7143f-130">Tlbimp.exe (Type Library Importer-Tool)</span><span class="sxs-lookup"><span data-stu-id="7143f-130">Tlbimp.exe (Type Library Importer)</span></span>](../tools/tlbimp-exe-type-library-importer.md)
- [<span data-ttu-id="7143f-131">Tlbexp.exe (Type Library Exporter-Tool)</span><span class="sxs-lookup"><span data-stu-id="7143f-131">Tlbexp.exe (Type Library Exporter)</span></span>](../tools/tlbexp-exe-type-library-exporter.md)
