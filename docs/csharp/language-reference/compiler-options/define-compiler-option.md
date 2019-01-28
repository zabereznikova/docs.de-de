---
title: -define (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /define
helpviewer_keywords:
- -define compiler option [C#]
- /define compiler option [C#]
- -d compiler option [C#]
- define compiler option [C#]
- /d compiler option [C#]
- d compiler option [C#]
ms.assetid: f17d7b4d-82d0-4133-8563-68cced1cac6e
ms.openlocfilehash: 56028bcf3b843a4f6884e2d7cc7d409621adba34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558818"
---
# <a name="-define-c-compiler-options"></a><span data-ttu-id="f0ed4-102">-define (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="f0ed4-102">-define (C# Compiler Options)</span></span>
<span data-ttu-id="f0ed4-103">Die Option **-define** definiert `name` als Symbol in allen Quellcodedateien Ihres Programms.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-103">The **-define** option defines `name` as a symbol in all source code files your program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0ed4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0ed4-104">Syntax</span></span>  
  
```console  
-define:name[;name2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f0ed4-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="f0ed4-105">Arguments</span></span>  
 <span data-ttu-id="f0ed4-106">`name`, `name2`</span><span class="sxs-lookup"><span data-stu-id="f0ed4-106">`name`, `name2`</span></span>  
 <span data-ttu-id="f0ed4-107">Der Name eines oder mehrerer Symbole, die Sie definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-107">The name of one or more symbols that you want to define.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0ed4-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0ed4-108">Remarks</span></span>  
 <span data-ttu-id="f0ed4-109">Die Option **-define** hat dieselbe Auswirkung wie die Verwendung einer [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)-Präprozessoranweisung, außer dass die Compileroption für alle Dateien im Projekt gültig ist.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-109">The **-define** option has the same effect as using a [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive except that the compiler option is in effect for all files in the project.</span></span> <span data-ttu-id="f0ed4-110">Ein Symbol bleibt in einer Quelldatei definiert, bis eine [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)-Anweisung in der Quelldatei die Definition entfernt.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-110">A symbol remains defined in a source file until an [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) directive in the source file removes the definition.</span></span> <span data-ttu-id="f0ed4-111">Wenn Sie die Option „-define“ verwenden, hat eine `#undef`-Anweisung in einer Datei keinerlei Auswirkung auf andere Quellcodedateien im Projekt.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-111">When you use the -define option, an `#undef` directive in one file has no effect on other source code files in the project.</span></span>  
  
 <span data-ttu-id="f0ed4-112">Sie können die durch diese Option erstellten Symbole in Verbindung mit [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), und [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) verwenden, um Quelldateien bedingt zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-112">You can use symbols created by this option with [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), and [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="f0ed4-113">**-d** ist die Kurzform von **-define**.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-113">**-d** is the short form of **-define**.</span></span>  
  
 <span data-ttu-id="f0ed4-114">Sie können mehrere Symbole mit **-define** definieren, indem Sie die Symbolnamen jeweils durch ein Semikolon oder Komma voneinander trennen.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-114">You can define multiple symbols with **-define** by using a semicolon or comma to separate symbol names.</span></span> <span data-ttu-id="f0ed4-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f0ed4-115">For example:</span></span>  
  
```console  
-define:DEBUG;TUESDAY  
```  
  
 <span data-ttu-id="f0ed4-116">Der C#-Compiler selbst definiert keine Symbole oder Makros, die Sie in Ihrem Quellcode verwenden können. Alle Symboldefinitionen müssen benutzerdefiniert sein.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-116">The C# compiler itself defines no symbols or macros that you can use in your source code; all symbol definitions must be user-defined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0ed4-117">Anders als in Programmiersprachen wie C++ ist es in C# bei Verwendung von `#define` nicht zulässig, einem Symbol einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-117">The C# `#define` does not allow a symbol to be given a value, as in languages such as C++.</span></span> <span data-ttu-id="f0ed4-118">Beispielsweise kann `#define` nicht zum Erstellen eines Makros oder zum Definieren einer Konstante verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-118">For example, `#define` cannot be used to create a macro or to define a constant.</span></span> <span data-ttu-id="f0ed4-119">Falls Sie eine Konstante definieren müssen, verwenden Sie eine `enum`-Variable.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-119">If you need to define a constant, use an `enum` variable.</span></span> <span data-ttu-id="f0ed4-120">Wenn Sie ein C++-übliches Makro erstellen möchten, erwägen Sie Alternativen wie Generika.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-120">If you want to create a C++ style macro, consider alternatives such as generics.</span></span> <span data-ttu-id="f0ed4-121">Da Makros sehr fehleranfällig sind, ist ihre Verwendung in C# nicht zugelassen. Es stehen jedoch sicherere Alternativen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-121">Since macros are notoriously error-prone, C# disallows their use but provides safer alternatives.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f0ed4-122">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="f0ed4-122">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="f0ed4-123">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-123">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="f0ed4-124">Geben Sie auf der Registerkarte **Erstellen** im Feld **Symbole für bedingte Kompilierung** das zu definierende Symbol ein.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-124">On the **Build** tab, type the symbol that is to be defined in the **Conditional compilation symbols** box.</span></span> <span data-ttu-id="f0ed4-125">Wenn Sie z.B. das folgende Codebeispiel verwenden, geben Sie im Textfeld einfach `xx` ein.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-125">For example, if you are using the code example that follows, just type `xx` into the text box.</span></span>  
  
 <span data-ttu-id="f0ed4-126">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0ed4-126">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0ed4-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0ed4-127">Example</span></span>  
  
```csharp  
// preprocessor_define.cs  
// compile with: -define:xx  
// or uncomment the next line  
// #define xx  
using System;  
public class Test   
{  
    public static void Main()   
    {  
        #if (xx)   
            Console.WriteLine("xx defined");  
        #else  
            Console.WriteLine("xx not defined");  
        #endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0ed4-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0ed4-128">See also</span></span>

- [<span data-ttu-id="f0ed4-129">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="f0ed4-129">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="f0ed4-130">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="f0ed4-130">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
