---
description: -warn (C#-Compileroptionen)
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
ms.custom: updateeachrelease
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: 55e80d0bd05e2119154210503bb277d743050e18
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139072"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="47454-103">-warn (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="47454-103">-warn (C# Compiler Options)</span></span>
<span data-ttu-id="47454-104">Die Option **-warn** gibt die vom Compiler anzuzeigende Warnstufe an.</span><span class="sxs-lookup"><span data-stu-id="47454-104">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47454-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="47454-105">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="47454-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="47454-106">Arguments</span></span>  
 `option`  
 <span data-ttu-id="47454-107">Die Warnstufe, die für die Kompilierung angezeigt werden soll: Niedrigere Zahlen zeigen nur schwerwiegendere Warnungen an, höhere Zahlen zeigen mehr Warnungen an.</span><span class="sxs-lookup"><span data-stu-id="47454-107">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="47454-108">Der Wert muss 0 (null) oder eine positive ganze Zahl sein:</span><span class="sxs-lookup"><span data-stu-id="47454-108">The value must be zero or a positive integer:</span></span>

|<span data-ttu-id="47454-109">Warnstufe</span><span class="sxs-lookup"><span data-stu-id="47454-109">Warning level</span></span>|<span data-ttu-id="47454-110">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="47454-110">Meaning</span></span>|
|-------------------|-------------|
|<span data-ttu-id="47454-111">0</span><span class="sxs-lookup"><span data-stu-id="47454-111">0</span></span>|<span data-ttu-id="47454-112">Deaktiviert die Ausgabe aller Warnungmeldungen</span><span class="sxs-lookup"><span data-stu-id="47454-112">Turns off emission of all warning messages.</span></span>|
|<span data-ttu-id="47454-113">1</span><span class="sxs-lookup"><span data-stu-id="47454-113">1</span></span>|<span data-ttu-id="47454-114">Zeigt schwerwiegende Warnmeldungen an</span><span class="sxs-lookup"><span data-stu-id="47454-114">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="47454-115">2</span><span class="sxs-lookup"><span data-stu-id="47454-115">2</span></span>|<span data-ttu-id="47454-116">Zeigt Warnungen der Stufe 1 sowie bestimmte, weniger schwerwiegende Warnungen an, z.B. Warnungen zum Ausblenden von Klassenmembern</span><span class="sxs-lookup"><span data-stu-id="47454-116">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="47454-117">3</span><span class="sxs-lookup"><span data-stu-id="47454-117">3</span></span>|<span data-ttu-id="47454-118">Zeigt Warnungen der Stufe 2 sowie bestimmte, weniger schwerwiegende Warnungen an, z.B. Warnungen zu Ausdrücken, immer nach `true` oder `false` ausgewertet werden</span><span class="sxs-lookup"><span data-stu-id="47454-118">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="47454-119">4 (Standard)</span><span class="sxs-lookup"><span data-stu-id="47454-119">4 (the default)</span></span>|<span data-ttu-id="47454-120">Zeigt die Warnungen aller drei Stufen sowie informative Warnungen an</span><span class="sxs-lookup"><span data-stu-id="47454-120">Displays all level 3 warnings plus informational warnings.</span></span>|
|<span data-ttu-id="47454-121">5</span><span class="sxs-lookup"><span data-stu-id="47454-121">5</span></span>|<span data-ttu-id="47454-122">Hier werden Warnungen der Stufe 4 sowie [zusätzliche Warnungen](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md) vom Compiler angezeigt, der in C# 9.0 enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="47454-122">Displays level 4 warnings plus [additional warnings](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md) from the compiler shipped with C# 9.0.</span></span>|
|<span data-ttu-id="47454-123">Höher als Stufe 5</span><span class="sxs-lookup"><span data-stu-id="47454-123">Greater than 5</span></span>|<span data-ttu-id="47454-124">Jeder Wert über Stufe 5 wird wie bei Stufe 5 behandelt.</span><span class="sxs-lookup"><span data-stu-id="47454-124">Any value greater than 5 will be treated as 5.</span></span> <span data-ttu-id="47454-125">Sie geben im Allgemeinen einen beliebig hohen Wert an (z. B. `9999`), um sicherzustellen, dass immer alle Warnungen vorhanden sind, wenn der Compiler mit neuen Warnstufen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="47454-125">You generally put arbitrary large value (for example, `9999`) to make sure you always have all warnings if the compiler is updated with new warning levels.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="47454-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="47454-126">Remarks</span></span>  
 <span data-ttu-id="47454-127">Um Informationen zu einem Fehler oder einer Warnung zu erhalten, schlagen Sie den Fehlercode im Hilfeindex nach.</span><span class="sxs-lookup"><span data-stu-id="47454-127">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="47454-128">Andere Möglichkeiten zum Abrufen von Informationen zu einem Fehler oder einer Warnung finden Sie unter [C#-Compilerfehler](../compiler-messages/index.md).</span><span class="sxs-lookup"><span data-stu-id="47454-128">For other ways to get information about an error or warning, see [C# Compiler Errors](../compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="47454-129">Verwenden Sie [-warnaserror](./warnaserror-compiler-option.md), um alle Warnungen als Fehler zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="47454-129">Use [-warnaserror](./warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="47454-130">Verwenden Sie [-nowarn](./nowarn-compiler-option.md), um bestimmte Warnungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="47454-130">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="47454-131">**-w** ist die Kurzform von **-warn**.</span><span class="sxs-lookup"><span data-stu-id="47454-131">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="47454-132">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="47454-132">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="47454-133">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="47454-133">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="47454-134">Klicken Sie auf die Eigenschaftenseite **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="47454-134">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="47454-135">Ändern Sie die Eigenschaft **Warnstufe**.</span><span class="sxs-lookup"><span data-stu-id="47454-135">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="47454-136">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="47454-136">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47454-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="47454-137">Example</span></span>  
 <span data-ttu-id="47454-138">Kompilieren Sie `in.cs`, und konfigurieren Sie den Compiler so, dass nur Warnungen der Stufe 1 angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="47454-138">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="47454-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="47454-139">See also</span></span>

- [<span data-ttu-id="47454-140">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="47454-140">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="47454-141">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="47454-141">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
