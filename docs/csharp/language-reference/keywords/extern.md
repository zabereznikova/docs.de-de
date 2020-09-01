---
description: extern-Modifizierer – C#-Referenz
title: extern-Modifizierer – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- extern_CSharpKeyword
- extern
helpviewer_keywords:
- DllImport attribute
- extern keyword [C#]
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
ms.openlocfilehash: 25eb5e6642d8b608bedcb4e9adadde4d84c2bae9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138968"
---
# <a name="extern-c-reference"></a><span data-ttu-id="03307-103">extern (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="03307-103">extern (C# Reference)</span></span>

<span data-ttu-id="03307-104">Der `extern`-Modifizierer wird verwendet, um eine extern implementierte Methode zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="03307-104">The `extern` modifier is used to declare a method that is implemented externally.</span></span> <span data-ttu-id="03307-105">Der `extern`-Modifizierer wird häufig mit dem `DllImport`-Attribut verwendet, wenn Sie nicht verwalteten Code mit Interop-Diensten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="03307-105">A common use of the `extern` modifier is with the `DllImport` attribute when you are using Interop services to call into unmanaged code.</span></span> <span data-ttu-id="03307-106">In diesem Fall muss die Methode auch als `static` deklariert werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="03307-106">In this case, the method must also be declared as `static`, as shown in the following example:</span></span>

```csharp
[DllImport("avifil32.dll")]
private static extern void AVIFileInit();
```

<span data-ttu-id="03307-107">Das `extern`-Schlüsselwort kann ebenso einen externen Assemblyalias definieren. Dadurch wird es möglich, aus einer einzigen Assembly heraus auf unterschiedliche Versionen derselben Komponente zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="03307-107">The `extern` keyword can also define an external assembly alias, which makes it possible to reference different versions of the same component from within a single assembly.</span></span> <span data-ttu-id="03307-108">Weitere Informationen finden Sie unter [extern-Alias](extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="03307-108">For more information, see [extern alias](extern-alias.md).</span></span>

<span data-ttu-id="03307-109">Es ist ein Fehler, den [abstract](abstract.md)-Modifizierer und den `extern`-Modifizierer gleichzeitig auf demselben Member anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="03307-109">It is an error to use the [abstract](abstract.md) and `extern` modifiers together to modify the same member.</span></span> <span data-ttu-id="03307-110">So bedeutet die Verwendung des `extern`-Modifizierers, dass die Methode außerhalb des C#-Codes implementiert wird, während bei Verwendung des `abstract`-Modifizierers die Methodenimplementierung nicht in der Klasse bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="03307-110">Using the `extern` modifier means that the method is implemented outside the C# code, whereas using the `abstract` modifier means that the method implementation is not provided in the class.</span></span>

<span data-ttu-id="03307-111">Die Verwendung des extern-Schlüsselworts ist in C# eingeschränkter als in C++.</span><span class="sxs-lookup"><span data-stu-id="03307-111">The extern keyword has more limited uses in C# than in C++.</span></span> <span data-ttu-id="03307-112">Informationen zum Vergleichen des C#-Schlüsselworts mit dem C++-Schlüsselwort finden Sie unter "Using extern to Specify Linkage" in der C++-Sprachreferenz.</span><span class="sxs-lookup"><span data-stu-id="03307-112">To compare the C# keyword with the C++ keyword, see Using extern to Specify Linkage in the C++ Language Reference.</span></span>

## <a name="example-1"></a><span data-ttu-id="03307-113">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="03307-113">Example 1</span></span>

<span data-ttu-id="03307-114">In diesem Beispiel empfängt das Programm eine Zeichenfolge vom Benutzer und zeigt sie in einem Meldungsfeld an.</span><span class="sxs-lookup"><span data-stu-id="03307-114">In this example, the program receives a string from the user and displays it inside a message box.</span></span> <span data-ttu-id="03307-115">Das Programm verwendet die `MessageBox`-Methode, die von der User32.dll-Bibliothek importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="03307-115">The program uses the `MessageBox` method imported from the User32.dll library.</span></span>

[!code-csharp[csrefKeywordsModifiers#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#8)]

## <a name="example-2"></a><span data-ttu-id="03307-116">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="03307-116">Example 2</span></span>

<span data-ttu-id="03307-117">Dieses Beispiel veranschaulicht ein C#-Programm, das eine C-Bibliothek aufruft (eine native DLL).</span><span class="sxs-lookup"><span data-stu-id="03307-117">This example illustrates a C# program that calls into a C library (a native DLL).</span></span>

1. <span data-ttu-id="03307-118">Erstellen Sie die folgende C-Datei mit dem Namen `cmdll.c`:</span><span class="sxs-lookup"><span data-stu-id="03307-118">Create the following C file and name it `cmdll.c`:</span></span>

    ```c
    // cmdll.c
    // Compile with: -LD
    int __declspec(dllexport) SampleMethod(int i)
    {
      return i*10;
    }
    ```

2. <span data-ttu-id="03307-119">Öffnen Sie ein Visual Studio x64 (oder x32) Native Tools-Eingabeaufforderungsfenster im Visual Studio-Installationsverzeichnis, und kompilieren Sie die `cmdll.c`-Datei, indem Sie in der Eingabeaufforderung **cl -LD cmdll.c** eingeben.</span><span class="sxs-lookup"><span data-stu-id="03307-119">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cmdll.c` file by typing **cl -LD cmdll.c** at the command prompt.</span></span>

3. <span data-ttu-id="03307-120">Erstellen Sie im gleichen Verzeichnis die folgende C#-Datei mit dem Namen `cm.cs`:</span><span class="sxs-lookup"><span data-stu-id="03307-120">In the same directory, create the following C# file and name it `cm.cs`:</span></span>

    ```csharp
    // cm.cs
    using System;
    using System.Runtime.InteropServices;
    public class MainClass
    {
        [DllImport("Cmdll.dll")]
          public static extern int SampleMethod(int x);

        static void Main()
        {
            Console.WriteLine("SampleMethod() returns {0}.", SampleMethod(5));
        }
    }
    ```

4. <span data-ttu-id="03307-121">Öffnen Sie ein Visual Studio x64 (oder x32) Native Tools-Eingabeaufforderungsfenster im Visual Studio-Installationsverzeichnis, und kompilieren Sie die `cm.cs`-Datei, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="03307-121">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cm.cs` file by typing:</span></span>

    > <span data-ttu-id="03307-122">**csc cm.cs** (für die x64-Eingabeaufforderung) oder **csc -platform:x86 cm.cs** (für die x32-Eingabeaufforderung)</span><span class="sxs-lookup"><span data-stu-id="03307-122">**csc cm.cs** (for the x64 command prompt) —or— **csc -platform:x86 cm.cs** (for the x32 command prompt)</span></span>

    <span data-ttu-id="03307-123">Dadurch wird die ausführbare Datei `cm.exe` erstellt.</span><span class="sxs-lookup"><span data-stu-id="03307-123">This will create the executable file `cm.exe`.</span></span>

5. <span data-ttu-id="03307-124">Führen Sie `cm.exe` aus.</span><span class="sxs-lookup"><span data-stu-id="03307-124">Run `cm.exe`.</span></span> <span data-ttu-id="03307-125">Die `SampleMethod`-Methode übergibt den Wert 5 an die DLL-Datei, die den mit 10 multiplizierten Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="03307-125">The `SampleMethod` method passes the value 5 to the DLL file, which returns the value multiplied by 10.</span></span>  <span data-ttu-id="03307-126">Das Programm erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="03307-126">The program produces the following output:</span></span>

    ```output
    SampleMethod() returns 50.
    ```

## <a name="c-language-specification"></a><span data-ttu-id="03307-127">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="03307-127">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="03307-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03307-128">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>
- [<span data-ttu-id="03307-129">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="03307-129">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="03307-130">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="03307-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="03307-131">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="03307-131">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="03307-132">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="03307-132">Modifiers</span></span>](index.md)
