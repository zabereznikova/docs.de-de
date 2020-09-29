---
description: -link (C#-Compileroptionen)
title: -link (C#-Compileroptionen)
ms.date: 07/20/2015
helpviewer_keywords:
- /l compiler option [C#]
- /link compiler option [C#]
- -l compiler option [C#]
- EmbedInteropTypes
- l compiler option [C#]
- embed interop types [COM Interop]
- -link compiler option [C#]
- link compiler option [C#]
ms.assetid: 00da70c6-9ea1-43c2-86f2-aa7f26c03475
ms.openlocfilehash: f6e654f4a24829de579ac94ef75b1c645fcb1685
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165831"
---
# <a name="-link-c-compiler-options"></a><span data-ttu-id="adcc2-103">-link (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="adcc2-103">-link (C# Compiler Options)</span></span>

<span data-ttu-id="adcc2-104">Bewirkt, dass der Compiler dem Projekt, das Sie aktuell kompilieren, COM-Typinformationen in den angegebenen Assemblys bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="adcc2-104">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>

## <a name="syntax"></a><span data-ttu-id="adcc2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="adcc2-105">Syntax</span></span>

```console
-link:fileList
// -or-
-l:fileList
```

## <a name="arguments"></a><span data-ttu-id="adcc2-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="adcc2-106">Arguments</span></span>

 `fileList`  
 <span data-ttu-id="adcc2-107">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="adcc2-107">Required.</span></span> <span data-ttu-id="adcc2-108">Durch Trennzeichen getrennte Liste von Assemblydateinamen.</span><span class="sxs-lookup"><span data-stu-id="adcc2-108">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="adcc2-109">Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="adcc2-109">If the file name contains a space, enclose the name in quotation marks.</span></span>

## <a name="remarks"></a><span data-ttu-id="adcc2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="adcc2-110">Remarks</span></span>

 <span data-ttu-id="adcc2-111">Die Option `-link` ermöglicht es Ihnen, eine Anwendung mit eingebetteten Typinformationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="adcc2-111">The `-link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="adcc2-112">Die Anwendung kann dann Typen in einer Runtime-Assembly verwenden, die die eingebetteten Typinformationen implementieren, ohne dass ein Verweis auf die Runtime-Assembly erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="adcc2-112">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="adcc2-113">Wenn verschiedene Versionen der Runtime-Assembly veröffentlicht werden, kann die Anwendung, die die eingebetteten Typinformationen enthält, mit den verschiedenen Versionen arbeiten, ohne neu kompiliert werden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="adcc2-113">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="adcc2-114">Ein Beispiel finden Sie unter [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](../../../standard/assembly/embed-types-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="adcc2-114">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](../../../standard/assembly/embed-types-visual-studio.md).</span></span>

 <span data-ttu-id="adcc2-115">Die Option `-link` ist besonders nützlich, wenn Sie COM-Interop verwenden.</span><span class="sxs-lookup"><span data-stu-id="adcc2-115">Using the `-link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="adcc2-116">Sie können COM-Typen einbetten, sodass für Ihre Anwendung keine primäre Interopassembly (PIA) auf dem Zielcomputer mehr erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="adcc2-116">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="adcc2-117">Die Option `-link` weist den Compiler an, die COM-Typinformationen aus der Interopassembly, auf die verwiesen wird, in den resultierenden kompilierten Code einzubetten.</span><span class="sxs-lookup"><span data-stu-id="adcc2-117">The `-link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="adcc2-118">Der COM-Typ wird durch den CLSID (GUID)-Wert identifiziert.</span><span class="sxs-lookup"><span data-stu-id="adcc2-118">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="adcc2-119">Dadurch kann Ihre Anwendung auf einem Zielcomputer ausgeführt werden, auf dem die gleichen COM-Typen mit den gleichen CLSID-Werten installiert sind.</span><span class="sxs-lookup"><span data-stu-id="adcc2-119">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="adcc2-120">Anwendungen, die Microsoft Office automatisieren, sind ein gutes Beispiel.</span><span class="sxs-lookup"><span data-stu-id="adcc2-120">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="adcc2-121">Da Anwendungen wie Office in der Regel den gleichen CLSID-Wert in den verschiedenen Versionen behalten, kann die Anwendung die COM-Typen, auf die verwiesen wird, verwenden, wenn .NET Framework 4 oder höher auf dem Zielcomputer installiert ist und die Anwendung Methoden, Eigenschaften oder Ereignisse verwendet, die in den COM-Typen, auf die verwiesen wird, enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="adcc2-121">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>

 <span data-ttu-id="adcc2-122">Die Option `-link` bettet nur Schnittstellen, Strukturen und Delegaten ein.</span><span class="sxs-lookup"><span data-stu-id="adcc2-122">The `-link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="adcc2-123">Das Einbetten von COM-Klassen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="adcc2-123">Embedding COM classes is not supported.</span></span>

> [!NOTE]
> <span data-ttu-id="adcc2-124">Wenn Sie eine Instanz eines eingebetteten COM-Typs in Ihrem Code erstellen, müssen Sie die Instanz mithilfe der entsprechenden Schnittstelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="adcc2-124">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="adcc2-125">Der Versuch, eine Instanz eines eingebetteten COM-Typs mit der Co-Klasse zu erstellen, verursacht einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="adcc2-125">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>

 <span data-ttu-id="adcc2-126">Fügen Sie zum Festlegen der Option `-link` in Visual Studio einen Assemblyverweis hinzu, und legen Sie die `Embed Interop Types`-Eigenschaft auf **TRUE** fest.</span><span class="sxs-lookup"><span data-stu-id="adcc2-126">To set the `-link` option in Visual Studio, add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="adcc2-127">Der Standardwert der `Embed Interop Types`-Eigenschaft ist **false**.</span><span class="sxs-lookup"><span data-stu-id="adcc2-127">The default for the `Embed Interop Types` property is **false**.</span></span>

 <span data-ttu-id="adcc2-128">Wenn Sie eine Verknüpfung mit einer COM-Assembly (Assembly A) erstellen, die selbst auf eine andere COM-Assembly (Assembly B) verweist, müssen Sie auch eine Verknüpfung mit Assembly B erstellen, wenn eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="adcc2-128">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>

- <span data-ttu-id="adcc2-129">Ein Typ von Assembly A erbt von einem Typ oder implementiert eine Schnittstelle aus Assembly B.</span><span class="sxs-lookup"><span data-stu-id="adcc2-129">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>

- <span data-ttu-id="adcc2-130">Es wird ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode aufgerufen, das/die über einen Rückgabetyp oder Parametertyp von Assembly B verfügt.</span><span class="sxs-lookup"><span data-stu-id="adcc2-130">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>

 <span data-ttu-id="adcc2-131">Wie die Compileroption [-reference](./reference-compiler-option.md) verwendet auch die Compileroption `-link` die Antwortdatei „Csc.rsp“, die auf häufig verwendete .NET-Assemblys verweist.</span><span class="sxs-lookup"><span data-stu-id="adcc2-131">Like the [-reference](./reference-compiler-option.md) compiler option, the `-link` compiler option uses the Csc.rsp response file, which references frequently used .NET assemblies.</span></span> <span data-ttu-id="adcc2-132">Verwenden Sie die Compileroption [-noconfig](./noconfig-compiler-option.md), wenn Sie nicht möchten, dass der Compiler die Datei „Csc.rsp“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="adcc2-132">Use the [-noconfig](./noconfig-compiler-option.md) compiler option if you do not want the compiler to use the Csc.rsp file.</span></span>

 <span data-ttu-id="adcc2-133">Die Kurzform von `-link` ist `-l`.</span><span class="sxs-lookup"><span data-stu-id="adcc2-133">The short form of `-link` is `-l`.</span></span>

## <a name="generics-and-embedded-types"></a><span data-ttu-id="adcc2-134">Generics und eingebettete Typen</span><span class="sxs-lookup"><span data-stu-id="adcc2-134">Generics and Embedded Types</span></span>

 <span data-ttu-id="adcc2-135">In den folgenden Abschnitten werden die Einschränkungen bei der Verwendung von generischen Typen in Anwendungen, die Interop-Typen einbetten, beschrieben.</span><span class="sxs-lookup"><span data-stu-id="adcc2-135">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>

### <a name="generic-interfaces"></a><span data-ttu-id="adcc2-136">Generische Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="adcc2-136">Generic Interfaces</span></span>

 <span data-ttu-id="adcc2-137">Generische Schnittstellen, die von einer Interopassembly eingebettet werden, können nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="adcc2-137">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="adcc2-138">Dies wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="adcc2-138">This is shown in the following example.</span></span>

 [!code-csharp[VbLinkCompilerCS#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#1)]

### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="adcc2-139">Typen, die generische Parameter aufweisen</span><span class="sxs-lookup"><span data-stu-id="adcc2-139">Types That Have Generic Parameters</span></span>

 <span data-ttu-id="adcc2-140">Typen, die über einen generischen Parameter verfügen, dessen Typ aus einer Interop-Assembly eingebettet wird, können nicht verwendet werden, wenn dieser Typ aus einer externen Assembly stammt.</span><span class="sxs-lookup"><span data-stu-id="adcc2-140">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="adcc2-141">Diese Einschränkung gilt nicht für Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="adcc2-141">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="adcc2-142">Nehmen Sie z.B. die <xref:Microsoft.Office.Interop.Excel.Range> Schnittstellen, die in der <xref:Microsoft.Office.Interop.Excel>-Assembly definiert wird.</span><span class="sxs-lookup"><span data-stu-id="adcc2-142">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="adcc2-143">Wenn eine Bibliothek Interop-Typen aus der <xref:Microsoft.Office.Interop.Excel>-Assembly einbettet und eine Methode verfügbar macht, die einen generischen Typ zurückgibt, der einen Parameter mit dem Typ <xref:Microsoft.Office.Interop.Excel.Range>-Schnittstelle hat, muss diese Methode eine generische Schnittstelle zurückgeben, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="adcc2-143">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>

[!code-csharp[VbLinkCompilerCS#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/utility.cs)]

 <span data-ttu-id="adcc2-144">Im folgenden Beispiel kann der Clientcode die Methode aufrufen, die die generische Schnittstelle <xref:System.Collections.IList> ohne Fehler zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="adcc2-144">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>

 [!code-csharp[VbLinkCompilerCS#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/vblinkcompilercs/cs/program.cs#5)]

## <a name="example"></a><span data-ttu-id="adcc2-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="adcc2-145">Example</span></span>

 <span data-ttu-id="adcc2-146">Der folgende Code kompiliert die Quelldatei `OfficeApp.cs` und Verweisassemblys aus `COMData1.dll` und `COMData2.dll`, um `OfficeApp.exe` zu produzieren.</span><span class="sxs-lookup"><span data-stu-id="adcc2-146">The following code compiles source file `OfficeApp.cs` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>

```csharp
csc -link:COMData1.dll,COMData2.dll -out:OfficeApp.exe OfficeApp.cs
```

## <a name="see-also"></a><span data-ttu-id="adcc2-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="adcc2-147">See also</span></span>

- [<span data-ttu-id="adcc2-148">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="adcc2-148">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="adcc2-149">Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="adcc2-149">Walkthrough: Embedding Types from Managed Assemblies</span></span>](../../../standard/assembly/embed-types-visual-studio.md)
- [<span data-ttu-id="adcc2-150">-reference (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="adcc2-150">-reference (C# Compiler Options)</span></span>](./reference-compiler-option.md)
- [<span data-ttu-id="adcc2-151">-noconfig (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="adcc2-151">-noconfig (C# Compiler Options)</span></span>](./noconfig-compiler-option.md)
- [<span data-ttu-id="adcc2-152">Erstellen über die Befehlszeile mit csc.exe</span><span class="sxs-lookup"><span data-stu-id="adcc2-152">Command-line Building With csc.exe</span></span>](./command-line-building-with-csc-exe.md)
- [<span data-ttu-id="adcc2-153">Überblick über die Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="adcc2-153">Interoperability Overview</span></span>](../../programming-guide/interop/interoperability-overview.md)
