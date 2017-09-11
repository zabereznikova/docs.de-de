---
title: C#-Compileroptionen
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.build.options
dev_langs:
- CSharp
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 02cfb7708959057de593506db55e4f31f5ab4fd0
ms.openlocfilehash: 7c5f5274a5685e50fb7f1d06771b0340200d1c3f
ms.contentlocale: de-de
ms.lasthandoff: 08/28/2017

---
# <a name="c-compiler-options"></a><span data-ttu-id="39ea5-102">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="39ea5-102">C# Compiler Options</span></span>
<span data-ttu-id="39ea5-103">Der Compiler generiert ausführbare Dateien (EXE), Dynamic Link Libraries (DLL) oder Codemodule (NETMODULE).</span><span class="sxs-lookup"><span data-stu-id="39ea5-103">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>  
  
 <span data-ttu-id="39ea5-104">Jede Compileroption ist in zwei Varianten verfügbar: **-option** und **/option**.</span><span class="sxs-lookup"><span data-stu-id="39ea5-104">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="39ea5-105">In der Dokumentation wird nur die **/option**-Variante gezeigt.</span><span class="sxs-lookup"><span data-stu-id="39ea5-105">The documentation only shows the **/option** form.</span></span>  
  
 <span data-ttu-id="39ea5-106">In Visual Web Developer 2008 legen Sie Compileroptionen in der WEB.CONFIG-Datei fest.</span><span class="sxs-lookup"><span data-stu-id="39ea5-106">In Visual Web Developer 2008, you set compiler options in the web.config file.</span></span> <span data-ttu-id="39ea5-107">Weitere Informationen finden Sie unter [\<compiler> Element](https://msdn.microsoft.com/library/y9x69bzw).</span><span class="sxs-lookup"><span data-stu-id="39ea5-107">For more information, see [\<compiler> Element](https://msdn.microsoft.com/library/y9x69bzw).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="39ea5-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="39ea5-108">In This Section</span></span>  
 [<span data-ttu-id="39ea5-109">Erstellen über die Befehlszeile mit csc.exe</span><span class="sxs-lookup"><span data-stu-id="39ea5-109">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 <span data-ttu-id="39ea5-110">Informationen zum Erstellen einer Visual C#-Anwendung über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="39ea5-110">Information about building a Visual C# application from the command line.</span></span>  
  
 [<span data-ttu-id="39ea5-111">Gewusst wie: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="39ea5-111">How to: Set Environment Variables for the Visual Studio Command Line</span></span>](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)  
 <span data-ttu-id="39ea5-112">Stellt Schritte zum Ausführen von „vsvars32.bat“ bereit, um Befehlszeilenbuilds zu ermöglichen</span><span class="sxs-lookup"><span data-stu-id="39ea5-112">Provides steps for running vsvars32.bat  to enable command-line builds.</span></span>  
  
 [<span data-ttu-id="39ea5-113">C#-Compileroptionen nach Kategorien sortiert</span><span class="sxs-lookup"><span data-stu-id="39ea5-113">C# Compiler Options Listed by Category</span></span>](../../../csharp/language-reference/compiler-options/listed-by-category.md)  
 <span data-ttu-id="39ea5-114">Eine nach Kategorien sortierte Liste der Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="39ea5-114">A categorical listing of the compiler options.</span></span>  
  
 [<span data-ttu-id="39ea5-115">C#-Compileroptionen alphabetisch sortiert</span><span class="sxs-lookup"><span data-stu-id="39ea5-115">C# Compiler Options Listed Alphabetically</span></span>](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)  
 <span data-ttu-id="39ea5-116">Eine alphabetisch sortierte Liste der Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="39ea5-116">An alphabetical listing of the compiler options.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="39ea5-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="39ea5-117">Related Sections</span></span>  
 [<span data-ttu-id="39ea5-118">Seite „Erstellen“, Projekt-Designer</span><span class="sxs-lookup"><span data-stu-id="39ea5-118">Build Page, Project Designer</span></span>](/visualstudio/ide/reference/build-page-project-designer-csharp)  
 <span data-ttu-id="39ea5-119">Festlegen von Eigenschaften, die das Kompilieren, Erstellen und Debuggen des Projekts regeln</span><span class="sxs-lookup"><span data-stu-id="39ea5-119">Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="39ea5-120">Enthält Informationen über benutzerdefinierte Buildschritte in Visual C#-Projekten</span><span class="sxs-lookup"><span data-stu-id="39ea5-120">Includes information about custom build steps in Visual C# projects.</span></span>  
  
 <span data-ttu-id="39ea5-121">[Default and Custom Builds](/visualstudio/ide/compiling-and-building-in-visual-studio) (Standardmäßige und benutzerdefinierte Builds)</span><span class="sxs-lookup"><span data-stu-id="39ea5-121">[Default and Custom Builds](/visualstudio/ide/compiling-and-building-in-visual-studio)</span></span>  
 <span data-ttu-id="39ea5-122">Informationen über Buildtypen und Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="39ea5-122">Information on build types and configurations.</span></span>  
  
 <span data-ttu-id="39ea5-123">[Preparing and Managing Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) (Vorbereiten und Verwalten von Builds)</span><span class="sxs-lookup"><span data-stu-id="39ea5-123">[Preparing and Managing Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)</span></span>  
 <span data-ttu-id="39ea5-124">Prozeduren zum Erstellen von Anwendungen in der Visual Studio-Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="39ea5-124">Procedures for building within the Visual Studio development environment.</span></span>

