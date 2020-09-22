---
title: Der Name "<name>" wurde nicht deklariert.
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: 76c1ab4fb5f1f8e4c76a06110f4b0f9026cca201
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871552"
---
# <a name="name-name-is-not-declared"></a><span data-ttu-id="a0d02-102">Der Name "\<name>" wurde nicht deklariert.</span><span class="sxs-lookup"><span data-stu-id="a0d02-102">Name '\<name>' is not declared</span></span>

<span data-ttu-id="a0d02-103">Eine-Anweisung verweist auf ein Programmier Element, aber der Compiler kann kein Element mit diesem exakten Namen finden.</span><span class="sxs-lookup"><span data-stu-id="a0d02-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="a0d02-104">**Fehler-ID:** BC30451</span><span class="sxs-lookup"><span data-stu-id="a0d02-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a0d02-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a0d02-105">To correct this error</span></span>  
  
1. <span data-ttu-id="a0d02-106">Überprüfen Sie die Schreibweise des Namens in der verweisenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a0d02-106">Check the spelling of the name in the referring statement.</span></span> <span data-ttu-id="a0d02-107">Bei Visual Basic wird die Groß-/Kleinschreibung nicht beachtet, aber jede andere Abweichung in der Rechtschreibung wird als vollständig anderer Name betrachtet.</span><span class="sxs-lookup"><span data-stu-id="a0d02-107">Visual Basic is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="a0d02-108">Beachten Sie, dass der Unterstrich (`_`) Teil des Namens und daher Teil der Schreibweise ist.</span><span class="sxs-lookup"><span data-stu-id="a0d02-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2. <span data-ttu-id="a0d02-109">Überprüfen Sie, ob der Member Access Operator ( `.` ) zwischen einem Objekt und seinem Member vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a0d02-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="a0d02-110">Wenn Sie z. B. ein <xref:System.Windows.Forms.TextBox> -Steuerelement namens `TextBox1`besitzen, müssen Sie für den Zugriff auf dessen <xref:System.Windows.Forms.TextBoxBase.Text%2A> -Eigenschaft `TextBox1.Text`eingeben.</span><span class="sxs-lookup"><span data-stu-id="a0d02-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="a0d02-111">Wenn Sie stattdessen `TextBox1Text`eingeben, haben Sie einen anderen Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="a0d02-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3. <span data-ttu-id="a0d02-112">Wenn die Schreibweise korrekt ist und die Syntax des Zugriffs auf Objektmember richtig ist, überprüfen Sie, ob das Element deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="a0d02-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="a0d02-113">Weitere Informationen finden Sie unter [deklarierte Elemente](../../programming-guide/language-features/declared-elements/index.md).</span><span class="sxs-lookup"><span data-stu-id="a0d02-113">For more information, see [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4. <span data-ttu-id="a0d02-114">Wenn das Programmier Element deklariert wurde, überprüfen Sie, ob es sich im Gültigkeitsbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="a0d02-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="a0d02-115">Wenn die verweisende Anweisung außerhalb des Bereichs liegt, der das Programmier Element deklariert, müssen Sie den Elementnamen möglicherweise qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="a0d02-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="a0d02-116">Weitere Informationen finden Sie unter [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="a0d02-116">For more information, see [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).</span></span>  

5. <span data-ttu-id="a0d02-117">Wenn Sie keinen voll qualifizierten Typ oder Typ und Elementnamen verwenden (z. b. bezieht sich der Code auf eine Eigenschaft als `MethodInfo.Name` anstelle von `System.Reflection.MethodInfo.Name` ), fügen Sie eine [Imports-Anweisung](../statements/imports-statement-net-namespace-and-type.md)hinzu.</span><span class="sxs-lookup"><span data-stu-id="a0d02-117">If you are not using a fully qualified type or type and member name (for example, your code refers to a property as `MethodInfo.Name` instead of `System.Reflection.MethodInfo.Name`), add an [Imports statement](../statements/imports-statement-net-namespace-and-type.md).</span></span>

6. <span data-ttu-id="a0d02-118">Wenn Sie versuchen, ein SDK-Projekt (ein Projekt mit einer \* VBPROJ-Datei, das mit der Zeile beginnt) zu kompilieren `<Project Sdk="Microsoft.NET.Sdk">` , und die Fehlermeldung auf einen Typ oder Member in der Microsoft.VisualBasic.dll-Assembly verweist, konfigurieren Sie die Anwendung so, dass Sie mit einem Verweis auf die Visual Basic Lauf Zeit Bibliothek kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="a0d02-118">If you are attempting to compile an SDK-style project (a project with a \*.vbproj file that begins with the line `<Project Sdk="Microsoft.NET.Sdk">`), and the error message refers to a type or member in the Microsoft.VisualBasic.dll assembly, configure your application to compile with a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="a0d02-119">Standardmäßig ist eine Teilmenge der Bibliothek in die Assembly in einem SDK-Stil eingebettet.</span><span class="sxs-lookup"><span data-stu-id="a0d02-119">By default, a subset of the library is embedded in your assembly in an SDK-style project.</span></span>

   <span data-ttu-id="a0d02-120">Beispielsweise kann das folgende Beispiel nicht kompiliert werden, da die- <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ChangeType%2A?displayProperty=fullName> Methode nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="a0d02-120">For example, the following example fails to compile because the <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ChangeType%2A?displayProperty=fullName> method cannot be found.</span></span> <span data-ttu-id="a0d02-121">Sie ist nicht in die Teilmenge der in der Anwendung enthaltenen Visual Basic Laufzeit eingebettet.</span><span class="sxs-lookup"><span data-stu-id="a0d02-121">It is not embedded in the subset of the Visual Basic Runtime included with your application.</span></span>  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb?highlight=7)]

   <span data-ttu-id="a0d02-122">Um diesen Fehler zu beheben, fügen Sie das-Element dem Projekt `<VBRuntime>Default</VBRuntime>` `<PropertyGroup>` Abschnitt hinzu, wie im folgenden Visual Basic Projektdatei gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0d02-122">To address this error, add the `<VBRuntime>Default</VBRuntime>` element to the projects `<PropertyGroup>` section, as the following Visual Basic project file shows.</span></span>

   [!code-xml[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a><span data-ttu-id="a0d02-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0d02-123">See also</span></span>

- [<span data-ttu-id="a0d02-124">Deklarationen und Konstanten: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="a0d02-124">Declarations and Constants Summary</span></span>](../keywords/declarations-and-constants-summary.md)
- [<span data-ttu-id="a0d02-125">Benennungskonventionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0d02-125">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="a0d02-126">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="a0d02-126">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="a0d02-127">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="a0d02-127">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
