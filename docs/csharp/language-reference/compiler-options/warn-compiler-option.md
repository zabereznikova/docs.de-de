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
ms.openlocfilehash: 17dd992edbec5ce444b53ed42b2b486282618672
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59315802"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="3a0f5-102">-warn (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="3a0f5-102">-warn (C# Compiler Options)</span></span>
<span data-ttu-id="3a0f5-103">Die Option **-warn** gibt die vom Compiler anzuzeigende Warnstufe an.</span><span class="sxs-lookup"><span data-stu-id="3a0f5-103">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a0f5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a0f5-104">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="3a0f5-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="3a0f5-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="3a0f5-106">Die Warnstufe, die für die Kompilierung angezeigt werden soll: Niedrigere Zahlen zeigen nur sehr schwerwiegende Warnungen an; höhere Zahlen zeigen mehr Warnungen an.</span><span class="sxs-lookup"><span data-stu-id="3a0f5-106">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="3a0f5-107">Gültige Werte sind 0–4:</span><span class="sxs-lookup"><span data-stu-id="3a0f5-107">Valid values are 0-4:</span></span>  
  
|<span data-ttu-id="3a0f5-108">Warnstufe</span><span class="sxs-lookup"><span data-stu-id="3a0f5-108">Warning level</span></span>|<span data-ttu-id="3a0f5-109">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="3a0f5-109">Meaning</span></span>|  
|-------------------|-------------|  
|<span data-ttu-id="3a0f5-110">0</span><span class="sxs-lookup"><span data-stu-id="3a0f5-110">0</span></span>|<span data-ttu-id="3a0f5-111">Deaktiviert die Ausgabe aller Warnungmeldungen</span><span class="sxs-lookup"><span data-stu-id="3a0f5-111">Turns off emission of all warning messages.</span></span>|  
|<span data-ttu-id="3a0f5-112">1</span><span class="sxs-lookup"><span data-stu-id="3a0f5-112">1</span></span>|<span data-ttu-id="3a0f5-113">Zeigt schwerwiegende Warnmeldungen an</span><span class="sxs-lookup"><span data-stu-id="3a0f5-113">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="3a0f5-114">2</span><span class="sxs-lookup"><span data-stu-id="3a0f5-114">2</span></span>|<span data-ttu-id="3a0f5-115">Zeigt Warnungen der Stufe 1 sowie bestimmte, weniger schwerwiegende Warnungen an, z.B. Warnungen zum Ausblenden von Klassenmembern</span><span class="sxs-lookup"><span data-stu-id="3a0f5-115">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="3a0f5-116">3</span><span class="sxs-lookup"><span data-stu-id="3a0f5-116">3</span></span>|<span data-ttu-id="3a0f5-117">Zeigt Warnungen der Stufe 2 sowie bestimmte, weniger schwerwiegende Warnungen an, z.B. Warnungen zu Ausdrücken, immer nach `true` oder `false` ausgewertet werden</span><span class="sxs-lookup"><span data-stu-id="3a0f5-117">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="3a0f5-118">4 (Standard)</span><span class="sxs-lookup"><span data-stu-id="3a0f5-118">4 (the default)</span></span>|<span data-ttu-id="3a0f5-119">Zeigt die Warnungen aller drei Stufen sowie informative Warnungen an</span><span class="sxs-lookup"><span data-stu-id="3a0f5-119">Displays all level 3 warnings plus informational warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a0f5-120">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="3a0f5-120">Remarks</span></span>  
 <span data-ttu-id="3a0f5-121">Um Informationen zu einem Fehler oder einer Warnung zu erhalten, schlagen Sie den Fehlercode im Hilfeindex nach.</span><span class="sxs-lookup"><span data-stu-id="3a0f5-121">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="3a0f5-122">Andere Möglichkeiten zum Abrufen von Informationen zu einem Fehler oder einer Warnung finden Sie unter [C#-Compilerfehler](../../../csharp/language-reference/compiler-messages/index.md).</span><span class="sxs-lookup"><span data-stu-id="3a0f5-122">For other ways to get information about an error or warning, see [C# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="3a0f5-123">Verwenden Sie [-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md), um alle Warnungen als Fehler zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="3a0f5-123">Use [-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="3a0f5-124">Verwenden Sie [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md), um bestimmte Warnungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="3a0f5-124">Use [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="3a0f5-125">**-w** ist die Kurzform von **-warn**.</span><span class="sxs-lookup"><span data-stu-id="3a0f5-125">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="3a0f5-126">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="3a0f5-126">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="3a0f5-127">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="3a0f5-127">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="3a0f5-128">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="3a0f5-128">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="3a0f5-129">Ändern Sie die Eigenschaft **Warnstufe**.</span><span class="sxs-lookup"><span data-stu-id="3a0f5-129">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="3a0f5-130">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="3a0f5-130">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a0f5-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3a0f5-131">Example</span></span>  
 <span data-ttu-id="3a0f5-132">Kompilieren Sie `in.cs`, und konfigurieren Sie den Compiler so, dass nur Warnungen der Stufe 1 angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="3a0f5-132">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a0f5-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a0f5-133">See also</span></span>

- [<span data-ttu-id="3a0f5-134">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="3a0f5-134">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="3a0f5-135">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="3a0f5-135">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
