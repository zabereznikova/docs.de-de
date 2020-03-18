---
title: -warn (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: 5b05e944a37e16fc1fcc422271be00c09a271a33
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602409"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="4f53f-102">-warn (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="4f53f-102">-warn (C# Compiler Options)</span></span>
<span data-ttu-id="4f53f-103">Die Option **-warn** gibt die vom Compiler anzuzeigende Warnstufe an.</span><span class="sxs-lookup"><span data-stu-id="4f53f-103">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f53f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f53f-104">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="4f53f-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="4f53f-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="4f53f-106">Die Warnstufe, die für die Kompilierung angezeigt werden soll: Niedrigere Zahlen zeigen nur schwerwiegendere Warnungen an, höhere Zahlen zeigen mehr Warnungen an.</span><span class="sxs-lookup"><span data-stu-id="4f53f-106">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="4f53f-107">Gültige Werte sind 0–4:</span><span class="sxs-lookup"><span data-stu-id="4f53f-107">Valid values are 0-4:</span></span>  
  
|<span data-ttu-id="4f53f-108">Warnstufe</span><span class="sxs-lookup"><span data-stu-id="4f53f-108">Warning level</span></span>|<span data-ttu-id="4f53f-109">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="4f53f-109">Meaning</span></span>|  
|-------------------|-------------|  
|<span data-ttu-id="4f53f-110">0</span><span class="sxs-lookup"><span data-stu-id="4f53f-110">0</span></span>|<span data-ttu-id="4f53f-111">Deaktiviert die Ausgabe aller Warnungmeldungen</span><span class="sxs-lookup"><span data-stu-id="4f53f-111">Turns off emission of all warning messages.</span></span>|  
|<span data-ttu-id="4f53f-112">1</span><span class="sxs-lookup"><span data-stu-id="4f53f-112">1</span></span>|<span data-ttu-id="4f53f-113">Zeigt schwerwiegende Warnmeldungen an</span><span class="sxs-lookup"><span data-stu-id="4f53f-113">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="4f53f-114">2</span><span class="sxs-lookup"><span data-stu-id="4f53f-114">2</span></span>|<span data-ttu-id="4f53f-115">Zeigt Warnungen der Stufe 1 sowie bestimmte, weniger schwerwiegende Warnungen an, z.B. Warnungen zum Ausblenden von Klassenmembern</span><span class="sxs-lookup"><span data-stu-id="4f53f-115">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="4f53f-116">3</span><span class="sxs-lookup"><span data-stu-id="4f53f-116">3</span></span>|<span data-ttu-id="4f53f-117">Zeigt Warnungen der Stufe 2 sowie bestimmte, weniger schwerwiegende Warnungen an, z.B. Warnungen zu Ausdrücken, immer nach `true` oder `false` ausgewertet werden</span><span class="sxs-lookup"><span data-stu-id="4f53f-117">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="4f53f-118">4 (Standard)</span><span class="sxs-lookup"><span data-stu-id="4f53f-118">4 (the default)</span></span>|<span data-ttu-id="4f53f-119">Zeigt die Warnungen aller drei Stufen sowie informative Warnungen an</span><span class="sxs-lookup"><span data-stu-id="4f53f-119">Displays all level 3 warnings plus informational warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f53f-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f53f-120">Remarks</span></span>  
 <span data-ttu-id="4f53f-121">Um Informationen zu einem Fehler oder einer Warnung zu erhalten, schlagen Sie den Fehlercode im Hilfeindex nach.</span><span class="sxs-lookup"><span data-stu-id="4f53f-121">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="4f53f-122">Andere Möglichkeiten zum Abrufen von Informationen zu einem Fehler oder einer Warnung finden Sie unter [C#-Compilerfehler](../compiler-messages/index.md).</span><span class="sxs-lookup"><span data-stu-id="4f53f-122">For other ways to get information about an error or warning, see [C# Compiler Errors](../compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="4f53f-123">Verwenden Sie [-warnaserror](./warnaserror-compiler-option.md), um alle Warnungen als Fehler zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="4f53f-123">Use [-warnaserror](./warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="4f53f-124">Verwenden Sie [-nowarn](./nowarn-compiler-option.md), um bestimmte Warnungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4f53f-124">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="4f53f-125">**-w** ist die Kurzform von **-warn**.</span><span class="sxs-lookup"><span data-stu-id="4f53f-125">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="4f53f-126">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="4f53f-126">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="4f53f-127">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="4f53f-127">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="4f53f-128">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="4f53f-128">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="4f53f-129">Ändern Sie die Eigenschaft **Warnstufe**.</span><span class="sxs-lookup"><span data-stu-id="4f53f-129">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="4f53f-130">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f53f-130">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f53f-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4f53f-131">Example</span></span>  
 <span data-ttu-id="4f53f-132">Kompilieren Sie `in.cs`, und konfigurieren Sie den Compiler so, dass nur Warnungen der Stufe 1 angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="4f53f-132">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f53f-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f53f-133">See also</span></span>

- [<span data-ttu-id="4f53f-134">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="4f53f-134">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="4f53f-135">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="4f53f-135">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
