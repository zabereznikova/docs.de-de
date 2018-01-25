---
title: -bugreport (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2a6c27454cc8f95b9662d6ae688471849c5cee0
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-bugreport-c-compiler-options"></a><span data-ttu-id="ec153-102">-bugreport (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="ec153-102">-bugreport (C# Compiler Options)</span></span>
<span data-ttu-id="ec153-103">Gibt an, dass Debuginformationen zum Zweck einer späteren Analyse in eine Datei eingefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ec153-103">Specifies that debug information should be placed in a file for later analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec153-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec153-104">Syntax</span></span>  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="ec153-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ec153-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="ec153-106">Der Name der Datei, die den Problembericht enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="ec153-106">The name of the file that you want to contain your bug report.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec153-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ec153-107">Remarks</span></span>  
 <span data-ttu-id="ec153-108">Die Option **-bugreport** gibt an, dass die folgende Informationen in `file` eingefügt werden soll:</span><span class="sxs-lookup"><span data-stu-id="ec153-108">The **-bugreport** option specifies that the following information should be placed in `file`:</span></span>  
  
-   <span data-ttu-id="ec153-109">Eine Kopie aller Quellcodedateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="ec153-109">A copy of all source code files in the compilation.</span></span>  
  
-   <span data-ttu-id="ec153-110">Eine Liste der bei der Kompilierung verwendeten Compileroptionen.</span><span class="sxs-lookup"><span data-stu-id="ec153-110">A listing of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="ec153-111">Versionsinformationen über den Compiler, die Laufzeit und das Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="ec153-111">Version information about your compiler, run time, and operating system.</span></span>  
  
-   <span data-ttu-id="ec153-112">Assemblys und Module, auf die verwiesen wird und die als Hexadezimalzahlen gespeichert sind, außer im Lieferumfang von .NET Framework und dem SDK enthaltene Assemblys.</span><span class="sxs-lookup"><span data-stu-id="ec153-112">Referenced assemblies and modules, saved as hexadecimal digits, except assemblies that ship with the .NET Framework and SDK.</span></span>  
  
-   <span data-ttu-id="ec153-113">Compilerausgabe, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ec153-113">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="ec153-114">Eine Beschreibung des Problems. Sie werden aufgefordert, diese Beschreibung einzugeben.</span><span class="sxs-lookup"><span data-stu-id="ec153-114">A description of the problem, which you will be prompted for.</span></span>  
  
-   <span data-ttu-id="ec153-115">Eine Beschreibung Ihres Vorschlags zur Beseitigung des Problems. Sie werden aufgefordert, diese Beschreibung einzugeben.</span><span class="sxs-lookup"><span data-stu-id="ec153-115">A description of how you think the problem should be fixed, which you will be prompted for.</span></span>  
  
 <span data-ttu-id="ec153-116">Wenn diese Option mit **-errorreport:prompt** oder **-errorreport:send** verwendet wird, werden die Informationen in der Datei an die Microsoft Corporation gesendet.</span><span class="sxs-lookup"><span data-stu-id="ec153-116">If this option is used with **-errorreport:prompt** or **-errorreport:send**, the information in the file will be sent to Microsoft Corporation.</span></span>  
  
 <span data-ttu-id="ec153-117">Da von allen Quellcodedateien Kopien in `file` gespeichert werden, empfiehlt es sich, den vermuteten Codefehler im kürzestmöglichen Programm zu reproduzieren.</span><span class="sxs-lookup"><span data-stu-id="ec153-117">Because a copy of all source code files will be placed in `file`, you might want to reproduce the suspected code defect in the shortest possible program.</span></span>  
  
 <span data-ttu-id="ec153-118">Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="ec153-118">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
 <span data-ttu-id="ec153-119">Beachten Sie, dass im Inhalt der generierten Datei Quellcode offen gelegt wird, was zu einer unbeabsichtigten Veröffentlichung von Informationen führen konnte.</span><span class="sxs-lookup"><span data-stu-id="ec153-119">Notice that contents of the generated file expose source code that could result in inadvertent information disclosure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec153-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec153-120">See Also</span></span>  
 [<span data-ttu-id="ec153-121">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="ec153-121">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="ec153-122">-errorreport (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="ec153-122">-errorreport (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)  
 [<span data-ttu-id="ec153-123">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="ec153-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
