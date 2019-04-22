---
title: -define (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: d0a483e7a3c9e9863db39e89d655cf172c1e8c81
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834308"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="54f8b-102">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54f8b-102">-define (Visual Basic)</span></span>
<span data-ttu-id="54f8b-103">Definiert Konstanten für die bedingte Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="54f8b-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54f8b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="54f8b-104">Syntax</span></span>  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="54f8b-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="54f8b-105">Arguments</span></span>  
  
|<span data-ttu-id="54f8b-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="54f8b-106">Term</span></span>|<span data-ttu-id="54f8b-107">Definition</span><span class="sxs-lookup"><span data-stu-id="54f8b-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="54f8b-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="54f8b-108">Required.</span></span> <span data-ttu-id="54f8b-109">Das zu definierende Symbol.</span><span class="sxs-lookup"><span data-stu-id="54f8b-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="54f8b-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="54f8b-110">Optional.</span></span> <span data-ttu-id="54f8b-111">Der Wert, der `symbol` zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="54f8b-111">The value to assign `symbol`.</span></span> <span data-ttu-id="54f8b-112">Wenn `value` ist eine Zeichenfolge, es muss durch den umgekehrten Schrägstrich/Anführungszeichen eingeschlossen sein (\\") anstelle von Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="54f8b-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="54f8b-113">Wurde kein Wert festgelegt, dann wird er als True angenommen.</span><span class="sxs-lookup"><span data-stu-id="54f8b-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54f8b-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="54f8b-114">Remarks</span></span>  
 <span data-ttu-id="54f8b-115">Die `-define` Option wirkt sich ähnlich wie die Verwendung einer `#Const` -präprozessoranweisung in der Quelldatei, außer diese mit definierten Konstanten `-define` öffentlich sind und auf alle Dateien im Projekt gelten.</span><span class="sxs-lookup"><span data-stu-id="54f8b-115">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="54f8b-116">Sie können Symbole, die mit dieser Option erstellt wurden, mit der `#If`...`Then`...`#Else`-Anweisung verwenden, um Quelldateien bedingt zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="54f8b-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="54f8b-117">`-d` ist die Kurzform der `-define`.</span><span class="sxs-lookup"><span data-stu-id="54f8b-117">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="54f8b-118">Sie können mehrere Symbole mit `-define` definieren, wenn Sie kommagetrennte Symboldefinitionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="54f8b-118">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="54f8b-119">So definieren Sie die integrierte Visual Studio-Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="54f8b-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="54f8b-120">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="54f8b-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="54f8b-121">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="54f8b-121">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="54f8b-122">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="54f8b-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="54f8b-123">3.  Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="54f8b-123">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="54f8b-124">4.  Ändern Sie den Wert in der **benutzerdefinierte Konstanten** Feld.</span><span class="sxs-lookup"><span data-stu-id="54f8b-124">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="54f8b-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="54f8b-125">Example</span></span>  
 <span data-ttu-id="54f8b-126">Der folgende Code definiert zwei konditionelle Compilerkonstanten und verwendet sie anschließend.</span><span class="sxs-lookup"><span data-stu-id="54f8b-126">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="54f8b-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54f8b-127">See also</span></span>

- [<span data-ttu-id="54f8b-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="54f8b-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="54f8b-129">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="54f8b-129">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="54f8b-130">#Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="54f8b-130">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="54f8b-131">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="54f8b-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
