---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: 5035466de4aa17c374824e1b0f02ed594731a9d3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716800"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="019de-102">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="019de-102">-define (Visual Basic)</span></span>
<span data-ttu-id="019de-103">Definiert Konstanten für die bedingte Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="019de-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="019de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="019de-104">Syntax</span></span>  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

<span data-ttu-id="019de-105">oder</span><span class="sxs-lookup"><span data-stu-id="019de-105">or</span></span>

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="019de-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="019de-106">Arguments</span></span>  
  
|<span data-ttu-id="019de-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="019de-107">Term</span></span>|<span data-ttu-id="019de-108">Definition</span><span class="sxs-lookup"><span data-stu-id="019de-108">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="019de-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="019de-109">Required.</span></span> <span data-ttu-id="019de-110">Das zu definierende Symbol.</span><span class="sxs-lookup"><span data-stu-id="019de-110">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="019de-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="019de-111">Optional.</span></span> <span data-ttu-id="019de-112">Der Wert, der `symbol` zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="019de-112">The value to assign `symbol`.</span></span> <span data-ttu-id="019de-113">Wenn `value` eine Zeichenfolge ist, muss sie von einer Kombination aus umgekehrtem Schrägstrich/Anführungszeichen (\\") statt Anführungszeichen umgeben sein.</span><span class="sxs-lookup"><span data-stu-id="019de-113">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="019de-114">Wurde kein Wert festgelegt, dann wird er als True angenommen.</span><span class="sxs-lookup"><span data-stu-id="019de-114">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="019de-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="019de-115">Remarks</span></span>  
 <span data-ttu-id="019de-116">Die Option `-define` hat einen ähnlichen Effekt wie das Verwenden einer `#Const`-Präprozessoranweisung in der Quelldatei, außer dass mit `-define` definierte Konstanten öffentlich sind und für alle Dateien im Projekt gelten.</span><span class="sxs-lookup"><span data-stu-id="019de-116">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="019de-117">Sie können Symbole, die mit dieser Option erstellt wurden, mit der `#If`...`Then`...`#Else`-Anweisung verwenden, um Quelldateien bedingt zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="019de-117">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="019de-118">`-d` ist die Kurzform von `-define`.</span><span class="sxs-lookup"><span data-stu-id="019de-118">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="019de-119">Sie können mehrere Symbole mit `-define` definieren, wenn Sie kommagetrennte Symboldefinitionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="019de-119">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="019de-120">So legen Sie -define in der integrierten Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="019de-120">To set -define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="019de-121">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="019de-121">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="019de-122">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="019de-122">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="019de-123">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="019de-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="019de-124">3.  Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="019de-124">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="019de-125">4.  Ändern Sie den Wert im Feld **Benutzerdefinierte Konstanten**.</span><span class="sxs-lookup"><span data-stu-id="019de-125">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="019de-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="019de-126">Example</span></span>  
 <span data-ttu-id="019de-127">Der folgende Code definiert zwei konditionelle Compilerkonstanten und verwendet sie anschließend.</span><span class="sxs-lookup"><span data-stu-id="019de-127">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="019de-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="019de-128">See also</span></span>

- [<span data-ttu-id="019de-129">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="019de-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="019de-130">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="019de-130">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="019de-131">#Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="019de-131">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="019de-132">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="019de-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
