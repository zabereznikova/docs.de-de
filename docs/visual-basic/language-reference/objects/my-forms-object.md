---
title: My.Forms-Objekt
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: db86704fdc8120ccac5f4489c80a515834ad888f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350374"
---
# <a name="myforms-object"></a><span data-ttu-id="985b1-102">My.Forms-Objekt</span><span class="sxs-lookup"><span data-stu-id="985b1-102">My.Forms Object</span></span>

<span data-ttu-id="985b1-103">Stellt Eigenschaften für den Zugriff auf eine Instanz der einzelnen im aktuellen Projekt deklarierten Windows Forms bereit.</span><span class="sxs-lookup"><span data-stu-id="985b1-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>

## <a name="remarks"></a><span data-ttu-id="985b1-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="985b1-104">Remarks</span></span>

<span data-ttu-id="985b1-105">Das `My.Forms`-Objekt stellt eine Instanz jedes Formulars im aktuellen Projekt bereit.</span><span class="sxs-lookup"><span data-stu-id="985b1-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="985b1-106">Der Name der Eigenschaft ist identisch mit dem Namen der Form, auf die die Eigenschaft zugreift.</span><span class="sxs-lookup"><span data-stu-id="985b1-106">The name of the property is the same as the name of the form that the property accesses.</span></span>

<span data-ttu-id="985b1-107">Sie können auf die vom `My.Forms` Objekt bereitgestellten Formulare zugreifen, indem Sie den Namen des Formulars ohne Qualifikation verwenden.</span><span class="sxs-lookup"><span data-stu-id="985b1-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="985b1-108">Da der Eigenschaftsname mit dem Typnamen des Formulars identisch ist, können Sie auf ein Formular zugreifen, als wäre es eine Standard Instanz.</span><span class="sxs-lookup"><span data-stu-id="985b1-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="985b1-109">`My.Forms.Form1.Show` entspricht beispielsweise `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="985b1-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>

<span data-ttu-id="985b1-110">Das `My.Forms`-Objekt macht nur die dem aktuellen Projekt zugeordneten Formulare verfügbar.</span><span class="sxs-lookup"><span data-stu-id="985b1-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="985b1-111">Der Zugriff auf Formulare, die in referenzierten DLLs deklariert sind, ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="985b1-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="985b1-112">Wenn Sie auf ein Formular zugreifen möchten, das eine DLL bereitstellt, müssen Sie den qualifizierten Namen des Formulars verwenden, der als *dllName*geschrieben wurde. *FormName*.</span><span class="sxs-lookup"><span data-stu-id="985b1-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>

<span data-ttu-id="985b1-113">Sie können die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>-Eigenschaft verwenden, um eine Sammlung aller geöffneten Formulare der Anwendung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="985b1-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>

<span data-ttu-id="985b1-114">Das-Objekt und seine Eigenschaften sind nur für Windows-Anwendungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="985b1-114">The object and its properties are available only for Windows applications.</span></span>

## <a name="properties"></a><span data-ttu-id="985b1-115">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="985b1-115">Properties</span></span>

<span data-ttu-id="985b1-116">Jede Eigenschaft des `My.Forms` Objekts ermöglicht den Zugriff auf eine Instanz eines Formulars im aktuellen Projekt.</span><span class="sxs-lookup"><span data-stu-id="985b1-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="985b1-117">Der Name der Eigenschaft ist identisch mit dem Namen der Form, auf die die Eigenschaft zugreift, und der Eigenschaftentyp entspricht dem Typ des Formulars.</span><span class="sxs-lookup"><span data-stu-id="985b1-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>

> [!NOTE]
> <span data-ttu-id="985b1-118">Wenn ein namens Konflikt vorliegt, ist der Eigenschaftsname für den Zugriff auf ein Formular *RootNamespace*_*Namespace*\_*FormName*.</span><span class="sxs-lookup"><span data-stu-id="985b1-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="985b1-119">Nehmen Sie beispielsweise zwei Formulare mit dem Namen `Form1.`, wenn sich eines dieser Formulare im Stamm Namespace befindet `WindowsApplication1` und im Namespace `Namespace1`auf dieses Formular über `My.Forms.WindowsApplication1_Namespace1_Form1`zugreifen.</span><span class="sxs-lookup"><span data-stu-id="985b1-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>

<span data-ttu-id="985b1-120">Das `My.Forms`-Objekt ermöglicht den Zugriff auf die Instanz des Haupt Formulars der Anwendung, das beim Start erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="985b1-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="985b1-121">Bei allen anderen Formularen erstellt das `My.Forms`-Objekt eine neue Instanz des Formulars, wenn darauf zugegriffen wird, und speichert es.</span><span class="sxs-lookup"><span data-stu-id="985b1-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="985b1-122">Bei nachfolgenden versuchen, auf diese Eigenschaft zuzugreifen, wird diese Instanz des Formulars zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="985b1-122">Subsequent attempts to access that property return that instance of the form.</span></span>

<span data-ttu-id="985b1-123">Sie können ein Formular verwerfen, indem Sie `Nothing` der-Eigenschaft für dieses Formular zuweisen.</span><span class="sxs-lookup"><span data-stu-id="985b1-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="985b1-124">Der Eigenschaften Setter Ruft die <xref:System.Windows.Forms.Form.Close%2A>-Methode des Formulars auf und weist dann `Nothing` dem gespeicherten Wert zu.</span><span class="sxs-lookup"><span data-stu-id="985b1-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="985b1-125">Wenn Sie der-Eigenschaft einen anderen Wert als `Nothing` zuweisen, löst der Setter eine <xref:System.ArgumentException>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="985b1-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="985b1-126">Sie können überprüfen, ob eine Eigenschaft des `My.Forms` Objekts eine Instanz des Formulars speichert, indem Sie den `Is`-oder `IsNot`-Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="985b1-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="985b1-127">Sie können diese Operatoren verwenden, um zu überprüfen, ob der Wert der Eigenschaft `Nothing`ist.</span><span class="sxs-lookup"><span data-stu-id="985b1-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>

> [!NOTE]
> <span data-ttu-id="985b1-128">In der Regel muss der `Is` oder `IsNot` Operator den Wert der-Eigenschaft lesen, um den Vergleich durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="985b1-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="985b1-129">Wenn die Eigenschaft derzeit jedoch `Nothing`speichert, erstellt die-Eigenschaft eine neue Instanz des Formulars und gibt diese Instanz zurück.</span><span class="sxs-lookup"><span data-stu-id="985b1-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="985b1-130">Der Visual Basic Compiler behandelt jedoch die Eigenschaften des `My.Forms` Objekts anders und ermöglicht es dem `Is` oder `IsNot` Operator, den Status der Eigenschaft zu überprüfen, ohne den Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="985b1-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>

## <a name="example"></a><span data-ttu-id="985b1-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="985b1-131">Example</span></span>

<span data-ttu-id="985b1-132">In diesem Beispiel wird der Titel des Standard `SidebarMenu` Formulars geändert.</span><span class="sxs-lookup"><span data-stu-id="985b1-132">This example changes the title of the default `SidebarMenu` form.</span></span>

[!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]

<span data-ttu-id="985b1-133">Damit dieses Beispiel funktioniert, muss das Projekt über ein Formular mit dem Namen `SidebarMenu`verfügen.</span><span class="sxs-lookup"><span data-stu-id="985b1-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>

<span data-ttu-id="985b1-134">Dieser Code funktioniert nur in einem Windows-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="985b1-134">This code will work only in a Windows Application project.</span></span>

## <a name="requirements"></a><span data-ttu-id="985b1-135">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="985b1-135">Requirements</span></span>

### <a name="availability-by-project-type"></a><span data-ttu-id="985b1-136">Verfügbarkeit nach Projekttyp</span><span class="sxs-lookup"><span data-stu-id="985b1-136">Availability by Project Type</span></span>

|<span data-ttu-id="985b1-137">Projekttyp:</span><span class="sxs-lookup"><span data-stu-id="985b1-137">Project type</span></span>|<span data-ttu-id="985b1-138">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="985b1-138">Available</span></span>|
|---|---|
|<span data-ttu-id="985b1-139">Windows-Anwendung</span><span class="sxs-lookup"><span data-stu-id="985b1-139">Windows Application</span></span>|<span data-ttu-id="985b1-140">**Ja**</span><span class="sxs-lookup"><span data-stu-id="985b1-140">**Yes**</span></span>|
|<span data-ttu-id="985b1-141">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="985b1-141">Class Library</span></span>|<span data-ttu-id="985b1-142">Nein</span><span class="sxs-lookup"><span data-stu-id="985b1-142">No</span></span>|
|<span data-ttu-id="985b1-143">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="985b1-143">Console Application</span></span>|<span data-ttu-id="985b1-144">Nein</span><span class="sxs-lookup"><span data-stu-id="985b1-144">No</span></span>|
|<span data-ttu-id="985b1-145">Windows-Steuerelement Bibliothek</span><span class="sxs-lookup"><span data-stu-id="985b1-145">Windows Control Library</span></span>|<span data-ttu-id="985b1-146">Nein</span><span class="sxs-lookup"><span data-stu-id="985b1-146">No</span></span>|
|<span data-ttu-id="985b1-147">Websteuer Element Bibliothek</span><span class="sxs-lookup"><span data-stu-id="985b1-147">Web Control Library</span></span>|<span data-ttu-id="985b1-148">Nein</span><span class="sxs-lookup"><span data-stu-id="985b1-148">No</span></span>|
|<span data-ttu-id="985b1-149">Windows-Dienst</span><span class="sxs-lookup"><span data-stu-id="985b1-149">Windows Service</span></span>|<span data-ttu-id="985b1-150">Nein</span><span class="sxs-lookup"><span data-stu-id="985b1-150">No</span></span>|
|<span data-ttu-id="985b1-151">Website</span><span class="sxs-lookup"><span data-stu-id="985b1-151">Web Site</span></span>|<span data-ttu-id="985b1-152">Nein</span><span class="sxs-lookup"><span data-stu-id="985b1-152">No</span></span>|

## <a name="see-also"></a><span data-ttu-id="985b1-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="985b1-153">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [<span data-ttu-id="985b1-154">Objekte</span><span class="sxs-lookup"><span data-stu-id="985b1-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)
- [<span data-ttu-id="985b1-155">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="985b1-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="985b1-156">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="985b1-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="985b1-157">Zugreifen auf Anwendungsformulare</span><span class="sxs-lookup"><span data-stu-id="985b1-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
