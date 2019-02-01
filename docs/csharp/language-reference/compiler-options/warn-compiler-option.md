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
ms.openlocfilehash: 5a4ecd1fbe5bb79a67d9df07d8f1a93830b03880
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499868"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="39e04-102">-warn (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="39e04-102">-warn (C# Compiler Options)</span></span>
<span data-ttu-id="39e04-103">Die Option **-warn** gibt die vom Compiler anzuzeigende Warnstufe an.</span><span class="sxs-lookup"><span data-stu-id="39e04-103">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39e04-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="39e04-104">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="39e04-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="39e04-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="39e04-106">Die Warnstufe, die für die Kompilierung angezeigt werden soll: Niedrigere Zahlen zeigen nur sehr schwerwiegende Warnungen an; höhere Zahlen zeigen mehr Warnungen an.</span><span class="sxs-lookup"><span data-stu-id="39e04-106">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="39e04-107">Gültige Werte sind 0–4:</span><span class="sxs-lookup"><span data-stu-id="39e04-107">Valid values are 0-4:</span></span>  
  
|<span data-ttu-id="39e04-108">Warnstufe</span><span class="sxs-lookup"><span data-stu-id="39e04-108">Warning level</span></span>|<span data-ttu-id="39e04-109">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="39e04-109">Meaning</span></span>|  
|-------------------|-------------|  
|<span data-ttu-id="39e04-110">0</span><span class="sxs-lookup"><span data-stu-id="39e04-110">0</span></span>|<span data-ttu-id="39e04-111">Deaktiviert die Ausgabe aller Warnungmeldungen</span><span class="sxs-lookup"><span data-stu-id="39e04-111">Turns off emission of all warning messages.</span></span>|  
|<span data-ttu-id="39e04-112">1</span><span class="sxs-lookup"><span data-stu-id="39e04-112">1</span></span>|<span data-ttu-id="39e04-113">Zeigt schwerwiegende Warnmeldungen an</span><span class="sxs-lookup"><span data-stu-id="39e04-113">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="39e04-114">2</span><span class="sxs-lookup"><span data-stu-id="39e04-114">2</span></span>|<span data-ttu-id="39e04-115">Zeigt Warnungen der Stufe 1 sowie bestimmte, weniger schwerwiegende Warnungen an, z.B. Warnungen zum Ausblenden von Klassenmembern</span><span class="sxs-lookup"><span data-stu-id="39e04-115">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="39e04-116">3</span><span class="sxs-lookup"><span data-stu-id="39e04-116">3</span></span>|<span data-ttu-id="39e04-117">Zeigt Warnungen der Stufe 2 sowie bestimmte, weniger schwerwiegende Warnungen an, z.B. Warnungen zu Ausdrücken, immer nach `true` oder `false` ausgewertet werden</span><span class="sxs-lookup"><span data-stu-id="39e04-117">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="39e04-118">4 (Standard)</span><span class="sxs-lookup"><span data-stu-id="39e04-118">4 (the default)</span></span>|<span data-ttu-id="39e04-119">Zeigt die Warnungen aller drei Stufen sowie informative Warnungen an</span><span class="sxs-lookup"><span data-stu-id="39e04-119">Displays all level 3 warnings plus informational warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39e04-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39e04-120">Remarks</span></span>  
 <span data-ttu-id="39e04-121">Um Informationen zu einem Fehler oder einer Warnung zu erhalten, schlagen Sie den Fehlercode im Hilfeindex nach.</span><span class="sxs-lookup"><span data-stu-id="39e04-121">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="39e04-122">Andere Möglichkeiten zum Abrufen von Informationen zu einem Fehler oder einer Warnung finden Sie unter [C#-Compilerfehler](../../../csharp/language-reference/compiler-messages/index.md).</span><span class="sxs-lookup"><span data-stu-id="39e04-122">For other ways to get information about an error or warning, see [C# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="39e04-123">Verwenden Sie [-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md), um alle Warnungen als Fehler zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="39e04-123">Use [-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="39e04-124">Verwenden Sie [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md), um bestimmte Warnungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="39e04-124">Use [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="39e04-125">**-w** ist die Kurzform von **-warn**.</span><span class="sxs-lookup"><span data-stu-id="39e04-125">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="39e04-126">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="39e04-126">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="39e04-127">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="39e04-127">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="39e04-128">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="39e04-128">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="39e04-129">Ändern Sie die Eigenschaft **Warnstufe**.</span><span class="sxs-lookup"><span data-stu-id="39e04-129">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="39e04-130">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="39e04-130">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39e04-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39e04-131">Example</span></span>  
 <span data-ttu-id="39e04-132">Kompilieren Sie `in.cs`, und konfigurieren Sie den Compiler so, dass nur Warnungen der Stufe 1 angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="39e04-132">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="39e04-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39e04-133">See also</span></span>

- [<span data-ttu-id="39e04-134">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="39e04-134">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="39e04-135">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="39e04-135">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
