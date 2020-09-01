---
description: -define (C#-Compileroptionen)
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
ms.openlocfilehash: 3b7a1c6e92d2c60ce289f29044774c3aa42ca84f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125877"
---
# <a name="-define-c-compiler-options"></a><span data-ttu-id="3af7a-103">-define (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="3af7a-103">-define (C# Compiler Options)</span></span>
<span data-ttu-id="3af7a-104">Die Option **-define** definiert `name` als Symbol in allen Quellcodedateien Ihres Programms.</span><span class="sxs-lookup"><span data-stu-id="3af7a-104">The **-define** option defines `name` as a symbol in all source code files your program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3af7a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3af7a-105">Syntax</span></span>  
  
```console  
-define:name[;name2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="3af7a-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="3af7a-106">Arguments</span></span>  
 <span data-ttu-id="3af7a-107">`name`, `name2`</span><span class="sxs-lookup"><span data-stu-id="3af7a-107">`name`, `name2`</span></span>  
 <span data-ttu-id="3af7a-108">Der Name eines oder mehrerer Symbole, die Sie definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3af7a-108">The name of one or more symbols that you want to define.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3af7a-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3af7a-109">Remarks</span></span>  
 <span data-ttu-id="3af7a-110">Die Option **-define** hat dieselbe Auswirkung wie die Verwendung einer [#define](../preprocessor-directives/preprocessor-define.md)-Präprozessoranweisung, außer dass die Compileroption für alle Dateien im Projekt gültig ist.</span><span class="sxs-lookup"><span data-stu-id="3af7a-110">The **-define** option has the same effect as using a [#define](../preprocessor-directives/preprocessor-define.md) preprocessor directive except that the compiler option is in effect for all files in the project.</span></span> <span data-ttu-id="3af7a-111">Ein Symbol bleibt in einer Quelldatei definiert, bis eine [#undef](../preprocessor-directives/preprocessor-undef.md)-Anweisung in der Quelldatei die Definition entfernt.</span><span class="sxs-lookup"><span data-stu-id="3af7a-111">A symbol remains defined in a source file until an [#undef](../preprocessor-directives/preprocessor-undef.md) directive in the source file removes the definition.</span></span> <span data-ttu-id="3af7a-112">Wenn Sie die Option „-define“ verwenden, hat eine `#undef`-Anweisung in einer Datei keinerlei Auswirkung auf andere Quellcodedateien im Projekt.</span><span class="sxs-lookup"><span data-stu-id="3af7a-112">When you use the -define option, an `#undef` directive in one file has no effect on other source code files in the project.</span></span>  
  
 <span data-ttu-id="3af7a-113">Sie können die durch diese Option erstellten Symbole in Verbindung mit [#if](../preprocessor-directives/preprocessor-if.md), [#else](../preprocessor-directives/preprocessor-else.md), [#elif](../preprocessor-directives/preprocessor-elif.md), und [#endif](../preprocessor-directives/preprocessor-endif.md) verwenden, um Quelldateien bedingt zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="3af7a-113">You can use symbols created by this option with [#if](../preprocessor-directives/preprocessor-if.md), [#else](../preprocessor-directives/preprocessor-else.md), [#elif](../preprocessor-directives/preprocessor-elif.md), and [#endif](../preprocessor-directives/preprocessor-endif.md) to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="3af7a-114">**-d** ist die Kurzform von **-define**.</span><span class="sxs-lookup"><span data-stu-id="3af7a-114">**-d** is the short form of **-define**.</span></span>  
  
 <span data-ttu-id="3af7a-115">Sie können mehrere Symbole mit **-define** definieren, indem Sie die Symbolnamen jeweils durch ein Semikolon oder Komma voneinander trennen.</span><span class="sxs-lookup"><span data-stu-id="3af7a-115">You can define multiple symbols with **-define** by using a semicolon or comma to separate symbol names.</span></span> <span data-ttu-id="3af7a-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3af7a-116">For example:</span></span>  
  
```console  
-define:DEBUG;TUESDAY  
```  
  
 <span data-ttu-id="3af7a-117">Der C#-Compiler selbst definiert keine Symbole oder Makros, die Sie in Ihrem Quellcode verwenden können. Alle Symboldefinitionen müssen benutzerdefiniert sein.</span><span class="sxs-lookup"><span data-stu-id="3af7a-117">The C# compiler itself defines no symbols or macros that you can use in your source code; all symbol definitions must be user-defined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3af7a-118">Anders als in Programmiersprachen wie C++ ist es in C# bei Verwendung von `#define` nicht zulässig, einem Symbol einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="3af7a-118">The C# `#define` does not allow a symbol to be given a value, as in languages such as C++.</span></span> <span data-ttu-id="3af7a-119">Beispielsweise kann `#define` nicht zum Erstellen eines Makros oder zum Definieren einer Konstante verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3af7a-119">For example, `#define` cannot be used to create a macro or to define a constant.</span></span> <span data-ttu-id="3af7a-120">Falls Sie eine Konstante definieren müssen, verwenden Sie eine `enum`-Variable.</span><span class="sxs-lookup"><span data-stu-id="3af7a-120">If you need to define a constant, use an `enum` variable.</span></span> <span data-ttu-id="3af7a-121">Wenn Sie ein C++-übliches Makro erstellen möchten, erwägen Sie Alternativen wie Generics.</span><span class="sxs-lookup"><span data-stu-id="3af7a-121">If you want to create a C++ style macro, consider alternatives such as generics.</span></span> <span data-ttu-id="3af7a-122">Da Makros sehr fehleranfällig sind, ist ihre Verwendung in C# nicht zugelassen. Es stehen jedoch sicherere Alternativen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3af7a-122">Since macros are notoriously error-prone, C# disallows their use but provides safer alternatives.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="3af7a-123">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="3af7a-123">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="3af7a-124">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="3af7a-124">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="3af7a-125">Geben Sie auf der Registerkarte **Erstellen** im Feld **Symbole für bedingte Kompilierung** das zu definierende Symbol ein.</span><span class="sxs-lookup"><span data-stu-id="3af7a-125">On the **Build** tab, type the symbol that is to be defined in the **Conditional compilation symbols** box.</span></span> <span data-ttu-id="3af7a-126">Wenn Sie z.B. das folgende Codebeispiel verwenden, geben Sie im Textfeld einfach `xx` ein.</span><span class="sxs-lookup"><span data-stu-id="3af7a-126">For example, if you are using the code example that follows, just type `xx` into the text box.</span></span>  
  
 <span data-ttu-id="3af7a-127">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.</span><span class="sxs-lookup"><span data-stu-id="3af7a-127">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3af7a-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3af7a-128">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3af7a-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3af7a-129">See also</span></span>

- [<span data-ttu-id="3af7a-130">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="3af7a-130">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="3af7a-131">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="3af7a-131">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
