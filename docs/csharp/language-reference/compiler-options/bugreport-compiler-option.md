---
title: -bugreport (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
ms.openlocfilehash: 0989678be070910c410d71717fe66679e1b70557
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69603080"
---
# <a name="-bugreport-c-compiler-options"></a><span data-ttu-id="db6ce-102">-bugreport (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="db6ce-102">-bugreport (C# Compiler Options)</span></span>
<span data-ttu-id="db6ce-103">Gibt an, dass Debuginformationen zum Zweck einer späteren Analyse in eine Datei eingefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="db6ce-103">Specifies that debug information should be placed in a file for later analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db6ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="db6ce-104">Syntax</span></span>  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="db6ce-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="db6ce-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="db6ce-106">Der Name der Datei, die den Problembericht enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="db6ce-106">The name of the file that you want to contain your bug report.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db6ce-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db6ce-107">Remarks</span></span>  
 <span data-ttu-id="db6ce-108">Die Option **-bugreport** gibt an, dass die folgende Informationen in `file` eingefügt werden soll:</span><span class="sxs-lookup"><span data-stu-id="db6ce-108">The **-bugreport** option specifies that the following information should be placed in `file`:</span></span>  
  
- <span data-ttu-id="db6ce-109">Eine Kopie aller Quellcodedateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="db6ce-109">A copy of all source code files in the compilation.</span></span>  
  
- <span data-ttu-id="db6ce-110">Eine Liste der bei der Kompilierung verwendeten Compileroptionen.</span><span class="sxs-lookup"><span data-stu-id="db6ce-110">A listing of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="db6ce-111">Versionsinformationen über den Compiler, die Laufzeit und das Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="db6ce-111">Version information about your compiler, run time, and operating system.</span></span>  
  
- <span data-ttu-id="db6ce-112">Assemblys und Module, auf die verwiesen wird und die als Hexadezimalzahlen gespeichert sind, außer im Lieferumfang von .NET Framework und dem SDK enthaltene Assemblys.</span><span class="sxs-lookup"><span data-stu-id="db6ce-112">Referenced assemblies and modules, saved as hexadecimal digits, except assemblies that ship with the .NET Framework and SDK.</span></span>  
  
- <span data-ttu-id="db6ce-113">Compilerausgabe, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="db6ce-113">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="db6ce-114">Eine Beschreibung des Problems. Sie werden aufgefordert, diese Beschreibung einzugeben.</span><span class="sxs-lookup"><span data-stu-id="db6ce-114">A description of the problem, which you will be prompted for.</span></span>  
  
- <span data-ttu-id="db6ce-115">Eine Beschreibung Ihres Vorschlags zur Beseitigung des Problems. Sie werden aufgefordert, diese Beschreibung einzugeben.</span><span class="sxs-lookup"><span data-stu-id="db6ce-115">A description of how you think the problem should be fixed, which you will be prompted for.</span></span>  
  
 <span data-ttu-id="db6ce-116">Wenn diese Option mit **-errorreport:prompt** oder **-errorreport:send** verwendet wird, werden die Informationen in der Datei an die Microsoft Corporation gesendet.</span><span class="sxs-lookup"><span data-stu-id="db6ce-116">If this option is used with **-errorreport:prompt** or **-errorreport:send**, the information in the file will be sent to Microsoft Corporation.</span></span>  
  
 <span data-ttu-id="db6ce-117">Da von allen Quellcodedateien Kopien in `file` gespeichert werden, empfiehlt es sich, den vermuteten Codefehler im kürzestmöglichen Programm zu reproduzieren.</span><span class="sxs-lookup"><span data-stu-id="db6ce-117">Because a copy of all source code files will be placed in `file`, you might want to reproduce the suspected code defect in the shortest possible program.</span></span>  
  
 <span data-ttu-id="db6ce-118">Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="db6ce-118">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
 <span data-ttu-id="db6ce-119">Beachten Sie, dass im Inhalt der generierten Datei Quellcode offen gelegt wird, was zu einer unbeabsichtigten Veröffentlichung von Informationen führen konnte.</span><span class="sxs-lookup"><span data-stu-id="db6ce-119">Notice that contents of the generated file expose source code that could result in inadvertent information disclosure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db6ce-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db6ce-120">See also</span></span>

- [<span data-ttu-id="db6ce-121">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="db6ce-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="db6ce-122">-errorreport (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="db6ce-122">-errorreport (C# Compiler Options)</span></span>](./errorreport-compiler-option.md)
- [<span data-ttu-id="db6ce-123">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="db6ce-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
