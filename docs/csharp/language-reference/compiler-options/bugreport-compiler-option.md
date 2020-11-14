---
description: -bugreport (C#-Compileroptionen)
title: -bugreport (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
ms.openlocfilehash: 1fb2efc9b12680e95767746c7e4e1ddacbdd2594
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93281505"
---
# <a name="-bugreport-c-compiler-options"></a><span data-ttu-id="80adc-103">-bugreport (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="80adc-103">-bugreport (C# Compiler Options)</span></span>

<span data-ttu-id="80adc-104">Gibt an, dass Debuginformationen zum Zweck einer späteren Analyse in eine Datei eingefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="80adc-104">Specifies that debug information should be placed in a file for later analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80adc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="80adc-105">Syntax</span></span>  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="80adc-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="80adc-106">Arguments</span></span>  

 `file`  
 <span data-ttu-id="80adc-107">Der Name der Datei, die den Problembericht enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="80adc-107">The name of the file that you want to contain your bug report.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80adc-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="80adc-108">Remarks</span></span>  

 <span data-ttu-id="80adc-109">Die Option **-bugreport** gibt an, dass die folgende Informationen in `file` eingefügt werden soll:</span><span class="sxs-lookup"><span data-stu-id="80adc-109">The **-bugreport** option specifies that the following information should be placed in `file`:</span></span>  
  
- <span data-ttu-id="80adc-110">Eine Kopie aller Quellcodedateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="80adc-110">A copy of all source code files in the compilation.</span></span>  
  
- <span data-ttu-id="80adc-111">Eine Liste der bei der Kompilierung verwendeten Compileroptionen.</span><span class="sxs-lookup"><span data-stu-id="80adc-111">A listing of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="80adc-112">Versionsinformationen über den Compiler, die Laufzeit und das Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="80adc-112">Version information about your compiler, run time, and operating system.</span></span>  
  
- <span data-ttu-id="80adc-113">Assemblys und Module, auf die verwiesen wird und die als Hexadezimalzahlen gespeichert sind, außer im Lieferumfang von .NET und dem .NET SDK enthaltene Assemblys.</span><span class="sxs-lookup"><span data-stu-id="80adc-113">Referenced assemblies and modules, saved as hexadecimal digits, except assemblies that are shipped with .NET and the .NET SDK.</span></span>  
  
- <span data-ttu-id="80adc-114">Compilerausgabe, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="80adc-114">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="80adc-115">Eine Beschreibung des Problems. Sie werden aufgefordert, diese Beschreibung einzugeben.</span><span class="sxs-lookup"><span data-stu-id="80adc-115">A description of the problem, which you will be prompted for.</span></span>  
  
- <span data-ttu-id="80adc-116">Eine Beschreibung Ihres Vorschlags zur Beseitigung des Problems. Sie werden aufgefordert, diese Beschreibung einzugeben.</span><span class="sxs-lookup"><span data-stu-id="80adc-116">A description of how you think the problem should be fixed, which you will be prompted for.</span></span>  
  
 <span data-ttu-id="80adc-117">Wenn diese Option mit **-errorreport:prompt** oder **-errorreport:send** verwendet wird, werden die Informationen in der Datei an die Microsoft Corporation gesendet.</span><span class="sxs-lookup"><span data-stu-id="80adc-117">If this option is used with **-errorreport:prompt** or **-errorreport:send** , the information in the file will be sent to Microsoft Corporation.</span></span>  
  
 <span data-ttu-id="80adc-118">Da von allen Quellcodedateien Kopien in `file` gespeichert werden, empfiehlt es sich, den vermuteten Codefehler im kürzestmöglichen Programm zu reproduzieren.</span><span class="sxs-lookup"><span data-stu-id="80adc-118">Because a copy of all source code files will be placed in `file`, you might want to reproduce the suspected code defect in the shortest possible program.</span></span>  
  
 <span data-ttu-id="80adc-119">Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="80adc-119">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
 <span data-ttu-id="80adc-120">Beachten Sie, dass im Inhalt der generierten Datei Quellcode offen gelegt wird, was zu einer unbeabsichtigten Veröffentlichung von Informationen führen konnte.</span><span class="sxs-lookup"><span data-stu-id="80adc-120">Notice that contents of the generated file expose source code that could result in inadvertent information disclosure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80adc-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80adc-121">See also</span></span>

- [<span data-ttu-id="80adc-122">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="80adc-122">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="80adc-123">-errorreport (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="80adc-123">-errorreport (C# Compiler Options)</span></span>](./errorreport-compiler-option.md)
- [<span data-ttu-id="80adc-124">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="80adc-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
