---
title: -define (Visual Basic)
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 136339c84ce80bff790c6683eef76065fb6d71ef
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-define-visual-basic"></a><span data-ttu-id="5c50e-102">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c50e-102">-define (Visual Basic)</span></span>
<span data-ttu-id="5c50e-103">Definiert Konstanten für die bedingte Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="5c50e-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c50e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c50e-104">Syntax</span></span>  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5c50e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="5c50e-105">Arguments</span></span>  
  
|<span data-ttu-id="5c50e-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="5c50e-106">Term</span></span>|<span data-ttu-id="5c50e-107">Definition</span><span class="sxs-lookup"><span data-stu-id="5c50e-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="5c50e-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5c50e-108">Required.</span></span> <span data-ttu-id="5c50e-109">Das zu definierende Symbol.</span><span class="sxs-lookup"><span data-stu-id="5c50e-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="5c50e-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="5c50e-110">Optional.</span></span> <span data-ttu-id="5c50e-111">Der Wert, der `symbol` zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c50e-111">The value to assign `symbol`.</span></span> <span data-ttu-id="5c50e-112">Wenn `value` ist eine Zeichenfolge, muss Sie von Sequenzen von umgekehrtem Schrägstrich/Anführungszeichen eingeschlossen sein (\\") anstelle von Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="5c50e-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="5c50e-113">Wurde kein Wert festgelegt, dann wird er als True angenommen.</span><span class="sxs-lookup"><span data-stu-id="5c50e-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c50e-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5c50e-114">Remarks</span></span>  
 <span data-ttu-id="5c50e-115">Die `-define` Option wirkt sich ähnlich wie die Verwendung einer `#Const` -Präprozessordirektive in der Quelldatei, außer diese mit definierte Konstanten `-define` öffentlich sind und auf alle Dateien im Projekt gelten.</span><span class="sxs-lookup"><span data-stu-id="5c50e-115">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="5c50e-116">Sie können Symbole, die mit dieser Option erstellt wurden, mit der `#If`...`Then`...`#Else`-Direktive verwenden, um Quelldateien bedingt zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="5c50e-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="5c50e-117">`-d` ist die Kurzform der `-define`.</span><span class="sxs-lookup"><span data-stu-id="5c50e-117">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="5c50e-118">Sie können mehrere Symbole mit `-define` definieren, wenn Sie kommagetrennte Symboldefinitionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="5c50e-118">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="5c50e-119">So definieren Sie die integrierte Visual Studio-Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="5c50e-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="5c50e-120">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="5c50e-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="5c50e-121">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5c50e-121">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="5c50e-122">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="5c50e-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="5c50e-123">3.  Klicken Sie auf **erweiterte**.</span><span class="sxs-lookup"><span data-stu-id="5c50e-123">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="5c50e-124">4.  Ändern Sie den Wert in der **benutzerdefinierte Konstanten** Feld.</span><span class="sxs-lookup"><span data-stu-id="5c50e-124">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5c50e-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c50e-125">Example</span></span>  
 <span data-ttu-id="5c50e-126">Der folgende Code definiert zwei konditionelle Compilerkonstanten und verwendet sie anschließend.</span><span class="sxs-lookup"><span data-stu-id="5c50e-126">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5c50e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c50e-127">See Also</span></span>  
 [<span data-ttu-id="5c50e-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="5c50e-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="5c50e-129">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="5c50e-129">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="5c50e-130">#Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5c50e-130">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
 [<span data-ttu-id="5c50e-131">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="5c50e-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
