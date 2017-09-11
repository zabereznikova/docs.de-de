---
title: -bugreport (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /bugreport
dev_langs:
- CSharp
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
caps.latest.revision: 20
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ccfea1aa7e51ad013418f61bc4478034c9a5d830
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="bugreport-c-compiler-options"></a><span data-ttu-id="15107-102">/bugreport (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="15107-102">/bugreport (C# Compiler Options)</span></span>
<span data-ttu-id="15107-103">Gibt an, dass Debuginformationen zum Zweck einer späteren Analyse in eine Datei eingefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="15107-103">Specifies that debug information should be placed in a file for later analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15107-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15107-104">Syntax</span></span>  
  
```console  
/bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="15107-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="15107-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="15107-106">Der Name der Datei, die den Problembericht enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="15107-106">The name of the file that you want to contain your bug report.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15107-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15107-107">Remarks</span></span>  
 <span data-ttu-id="15107-108">Die **/bugreport** Option gibt an, dass die folgende Informationen in eingefügt werden soll `file`:</span><span class="sxs-lookup"><span data-stu-id="15107-108">The **/bugreport** option specifies that the following information should be placed in `file`:</span></span>  
  
-   <span data-ttu-id="15107-109">Eine Kopie aller Quellcodedateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="15107-109">A copy of all source code files in the compilation.</span></span>  
  
-   <span data-ttu-id="15107-110">Eine Liste der bei der Kompilierung verwendeten Compileroptionen.</span><span class="sxs-lookup"><span data-stu-id="15107-110">A listing of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="15107-111">Versionsinformationen über den Compiler, die Laufzeit und das Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="15107-111">Version information about your compiler, run time, and operating system.</span></span>  
  
-   <span data-ttu-id="15107-112">Assemblys und Module, auf die verwiesen wird und die als Hexadezimalzahlen gespeichert sind, außer im Lieferumfang von .NET Framework und dem SDK enthaltene Assemblys.</span><span class="sxs-lookup"><span data-stu-id="15107-112">Referenced assemblies and modules, saved as hexadecimal digits, except assemblies that ship with the .NET Framework and SDK.</span></span>  
  
-   <span data-ttu-id="15107-113">Compilerausgabe, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="15107-113">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="15107-114">Eine Beschreibung des Problems. Sie werden aufgefordert, diese Beschreibung einzugeben.</span><span class="sxs-lookup"><span data-stu-id="15107-114">A description of the problem, which you will be prompted for.</span></span>  
  
-   <span data-ttu-id="15107-115">Eine Beschreibung Ihres Vorschlags zur Beseitigung des Problems. Sie werden aufgefordert, diese Beschreibung einzugeben.</span><span class="sxs-lookup"><span data-stu-id="15107-115">A description of how you think the problem should be fixed, which you will be prompted for.</span></span>  
  
 <span data-ttu-id="15107-116">Wenn diese Option mit **/errorreport:prompt** oder **/errorreport:send** verwendet wird, werden die Informationen in der Datei an die Microsoft Corporation gesendet.</span><span class="sxs-lookup"><span data-stu-id="15107-116">If this option is used with **/errorreport:prompt** or **/errorreport:send**, the information in the file will be sent to Microsoft Corporation.</span></span>  
  
 <span data-ttu-id="15107-117">Da von allen Quellcodedateien Kopien in `file` gespeichert werden, empfiehlt es sich, den vermuteten Codefehler im kürzestmöglichen Programm zu reproduzieren.</span><span class="sxs-lookup"><span data-stu-id="15107-117">Because a copy of all source code files will be placed in `file`, you might want to reproduce the suspected code defect in the shortest possible program.</span></span>  
  
 <span data-ttu-id="15107-118">Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="15107-118">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
 <span data-ttu-id="15107-119">Beachten Sie, dass im Inhalt der generierten Datei Quellcode offen gelegt wird, was zu einer unbeabsichtigten Veröffentlichung von Informationen führen konnte.</span><span class="sxs-lookup"><span data-stu-id="15107-119">Notice that contents of the generated file expose source code that could result in inadvertent information disclosure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15107-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15107-120">See Also</span></span>  
 <span data-ttu-id="15107-121">[C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="15107-121">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 <span data-ttu-id="15107-122">[/errorreport (C# Compiler Options) (/errorreport (C#-Compileroptionen))](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="15107-122">[/errorreport (C# Compiler Options)](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md) </span></span>  
 [<span data-ttu-id="15107-123">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="15107-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

