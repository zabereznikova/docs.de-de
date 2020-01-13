---
title: extern-Modifizierer – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- extern_CSharpKeyword
- extern
helpviewer_keywords:
- DllImport attribute
- extern keyword [C#]
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
ms.openlocfilehash: c121d810e64b5fa27f105f814253c0752e028a95
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713537"
---
# <a name="extern-c-reference"></a><span data-ttu-id="83ebd-102">extern (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="83ebd-102">extern (C# Reference)</span></span>

<span data-ttu-id="83ebd-103">Der `extern`-Modifizierer wird verwendet, um eine extern implementierte Methode zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="83ebd-103">The `extern` modifier is used to declare a method that is implemented externally.</span></span> <span data-ttu-id="83ebd-104">Der `extern`-Modifizierer wird häufig mit dem `DllImport`-Attribut verwendet, wenn Sie nicht verwalteten Code mit Interop-Diensten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="83ebd-104">A common use of the `extern` modifier is with the `DllImport` attribute when you are using Interop services to call into unmanaged code.</span></span> <span data-ttu-id="83ebd-105">In diesem Fall muss die Methode auch als `static` deklariert werden, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="83ebd-105">In this case, the method must also be declared as `static`, as shown in the following example:</span></span>

```csharp
[DllImport("avifil32.dll")]
private static extern void AVIFileInit();
```

<span data-ttu-id="83ebd-106">Das `extern`-Schlüsselwort kann ebenso einen externen Assemblyalias definieren. Dadurch wird es möglich, aus einer einzigen Assembly heraus auf unterschiedliche Versionen derselben Komponente zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="83ebd-106">The `extern` keyword can also define an external assembly alias, which makes it possible to reference different versions of the same component from within a single assembly.</span></span> <span data-ttu-id="83ebd-107">Weitere Informationen finden Sie unter [extern-Alias](extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="83ebd-107">For more information, see [extern alias](extern-alias.md).</span></span>

<span data-ttu-id="83ebd-108">Es ist ein Fehler, den [abstract](abstract.md)-Modifizierer und den `extern`-Modifizierer gleichzeitig auf demselben Member anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="83ebd-108">It is an error to use the [abstract](abstract.md) and `extern` modifiers together to modify the same member.</span></span> <span data-ttu-id="83ebd-109">So bedeutet die Verwendung des `extern`-Modifizierers, dass die Methode außerhalb des C#-Codes implementiert wird, während bei Verwendung des `abstract`-Modifizierers die Methodenimplementierung nicht in der Klasse bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="83ebd-109">Using the `extern` modifier means that the method is implemented outside the C# code, whereas using the `abstract` modifier means that the method implementation is not provided in the class.</span></span>

<span data-ttu-id="83ebd-110">Die Verwendung des extern-Schlüsselworts ist in C# eingeschränkter als in C++.</span><span class="sxs-lookup"><span data-stu-id="83ebd-110">The extern keyword has more limited uses in C# than in C++.</span></span> <span data-ttu-id="83ebd-111">Informationen zum Vergleichen des C#-Schlüsselworts mit dem C++-Schlüsselwort finden Sie unter "Using extern to Specify Linkage" in der C++-Sprachreferenz.</span><span class="sxs-lookup"><span data-stu-id="83ebd-111">To compare the C# keyword with the C++ keyword, see Using extern to Specify Linkage in the C++ Language Reference.</span></span>

## <a name="example-1"></a><span data-ttu-id="83ebd-112">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="83ebd-112">Example 1</span></span>

<span data-ttu-id="83ebd-113">In diesem Beispiel empfängt das Programm eine Zeichenfolge vom Benutzer und zeigt sie in einem Meldungsfeld an.</span><span class="sxs-lookup"><span data-stu-id="83ebd-113">In this example, the program receives a string from the user and displays it inside a message box.</span></span> <span data-ttu-id="83ebd-114">Das Programm verwendet die `MessageBox`-Methode, die von der User32.dll-Bibliothek importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="83ebd-114">The program uses the `MessageBox` method imported from the User32.dll library.</span></span>

[!code-csharp[csrefKeywordsModifiers#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#8)]

## <a name="example-2"></a><span data-ttu-id="83ebd-115">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="83ebd-115">Example 2</span></span>

<span data-ttu-id="83ebd-116">Dieses Beispiel veranschaulicht ein C#-Programm, das eine C-Bibliothek aufruft (eine native DLL).</span><span class="sxs-lookup"><span data-stu-id="83ebd-116">This example illustrates a C# program that calls into a C library (a native DLL).</span></span>

1. <span data-ttu-id="83ebd-117">Erstellen Sie die folgende C-Datei mit dem Namen `cmdll.c`:</span><span class="sxs-lookup"><span data-stu-id="83ebd-117">Create the following C file and name it `cmdll.c`:</span></span>

    ```c
    // cmdll.c
    // Compile with: -LD
    int __declspec(dllexport) SampleMethod(int i)
    {
      return i*10;
    }
    ```

2. <span data-ttu-id="83ebd-118">Öffnen Sie ein Visual Studio x64 (oder x32) Native Tools-Eingabeaufforderungsfenster im Visual Studio-Installationsverzeichnis, und kompilieren Sie die `cmdll.c`-Datei, indem Sie in der Eingabeaufforderung **cl -LD cmdll.c** eingeben.</span><span class="sxs-lookup"><span data-stu-id="83ebd-118">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cmdll.c` file by typing **cl -LD cmdll.c** at the command prompt.</span></span>

3. <span data-ttu-id="83ebd-119">Erstellen Sie im gleichen Verzeichnis die folgende C#-Datei mit dem Namen `cm.cs`:</span><span class="sxs-lookup"><span data-stu-id="83ebd-119">In the same directory, create the following C# file and name it `cm.cs`:</span></span>

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

4. <span data-ttu-id="83ebd-120">Öffnen Sie ein Visual Studio x64 (oder x32) Native Tools-Eingabeaufforderungsfenster im Visual Studio-Installationsverzeichnis, und kompilieren Sie die `cm.cs`-Datei, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="83ebd-120">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cm.cs` file by typing:</span></span>

    > <span data-ttu-id="83ebd-121">**csc cm.cs** (für die x64-Eingabeaufforderung) oder **csc -platform:x86 cm.cs** (für die x32-Eingabeaufforderung)</span><span class="sxs-lookup"><span data-stu-id="83ebd-121">**csc cm.cs** (for the x64 command prompt) —or— **csc -platform:x86 cm.cs** (for the x32 command prompt)</span></span>

    <span data-ttu-id="83ebd-122">Dadurch wird die ausführbare Datei `cm.exe` erstellt.</span><span class="sxs-lookup"><span data-stu-id="83ebd-122">This will create the executable file `cm.exe`.</span></span>

5. <span data-ttu-id="83ebd-123">Führen Sie aus `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="83ebd-123">Run `cm.exe`.</span></span> <span data-ttu-id="83ebd-124">Die `SampleMethod`-Methode übergibt den Wert 5 an die DLL-Datei, die den mit 10 multiplizierten Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="83ebd-124">The `SampleMethod` method passes the value 5 to the DLL file, which returns the value multiplied by 10.</span></span>  <span data-ttu-id="83ebd-125">Das Programm erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="83ebd-125">The program produces the following output:</span></span>

    ```output
    SampleMethod() returns 50.
    ```

## <a name="c-language-specification"></a><span data-ttu-id="83ebd-126">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="83ebd-126">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="83ebd-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83ebd-127">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>
- [<span data-ttu-id="83ebd-128">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="83ebd-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="83ebd-129">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="83ebd-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="83ebd-130">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="83ebd-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="83ebd-131">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="83ebd-131">Modifiers</span></span>](index.md)
