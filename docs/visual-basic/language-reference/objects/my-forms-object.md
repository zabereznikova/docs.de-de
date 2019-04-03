---
title: My.Forms-Objekt (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 4998097b910a504461a34af3cc159ddb1c74cc62
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832553"
---
# <a name="myforms-object"></a><span data-ttu-id="a0717-102">My.Forms-Objekt</span><span class="sxs-lookup"><span data-stu-id="a0717-102">My.Forms Object</span></span>
<span data-ttu-id="a0717-103">Stellt Eigenschaften bereit, für den Zugriff auf eine Instanz von jedem Windows-Formular, das im aktuellen Projekt deklariert.</span><span class="sxs-lookup"><span data-stu-id="a0717-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0717-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0717-104">Remarks</span></span>  
 <span data-ttu-id="a0717-105">Die `My.Forms` Objekt stellt eine Instanz jedes Formular im aktuellen Projekt.</span><span class="sxs-lookup"><span data-stu-id="a0717-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="a0717-106">Der Name der Eigenschaft ist identisch mit den Namen des Formulars, das die Eigenschaft zugreift.</span><span class="sxs-lookup"><span data-stu-id="a0717-106">The name of the property is the same as the name of the form that the property accesses.</span></span>   
  
 <span data-ttu-id="a0717-107">Sie können die bereitgestellten Formulare zugreifen der `My.Forms` Objekt mit dem Namen des Formulars ohne Qualifizierung.</span><span class="sxs-lookup"><span data-stu-id="a0717-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="a0717-108">Da die Namen der Eigenschaft den Namen des Formulars Typ identisch ist, können Sie auf ein Formular zugreifen, als hätte sie eine Standardinstanz.</span><span class="sxs-lookup"><span data-stu-id="a0717-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="a0717-109">`My.Forms.Form1.Show` entspricht beispielsweise `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="a0717-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>  
  
 <span data-ttu-id="a0717-110">Die `My.Forms` Objekt verfügbar macht, nur die Formulare, die mit dem aktuellen Projekt verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="a0717-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="a0717-111">Er bietet Zugriff auf Formulare, die in referenzierten DLLs deklariert.</span><span class="sxs-lookup"><span data-stu-id="a0717-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="a0717-112">Sie müssen ein Formular für den Zugriff auf, der eine DLL-Datei enthält den qualifizierten Namen des Formulars, geschrieben als verwenden *DllName*. *Formularname*.</span><span class="sxs-lookup"><span data-stu-id="a0717-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>  
  
 <span data-ttu-id="a0717-113">Sie können die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> Eigenschaft zum Abrufen einer Auflistung der offenen Formulare aller Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="a0717-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>  
  
 <span data-ttu-id="a0717-114">Das Objekt und seine Eigenschaften sind nur für Windows-Anwendungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a0717-114">The object and its properties are available only for Windows applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a0717-115">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a0717-115">Properties</span></span>  
 <span data-ttu-id="a0717-116">Jede Eigenschaft der `My.Forms` -Objekt bietet Zugriff auf eine Instanz eines Formulars im aktuellen Projekt.</span><span class="sxs-lookup"><span data-stu-id="a0717-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="a0717-117">Der Name der Eigenschaft ist identisch mit den Namen des Formulars, das die Eigenschaft zugreift, und der Eigenschaftentyp entspricht dem Typ des Formulars.</span><span class="sxs-lookup"><span data-stu-id="a0717-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0717-118">Bei ein Namenskonflikt wird der Eigenschaftsname Zugriff auf ein Formular ist *RootNamespace*_*Namespace*\_*Formularname*.</span><span class="sxs-lookup"><span data-stu-id="a0717-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="a0717-119">Betrachten Sie z. B. zwei Formulare mit dem Namen `Form1.`eines dieser Formulare im RootNamespace ist `WindowsApplication1` und im Namespace `Namespace1`, greifen Sie auf diesem Formular kann über `My.Forms.WindowsApplication1_Namespace1_Form1`.</span><span class="sxs-lookup"><span data-stu-id="a0717-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>  
  
 <span data-ttu-id="a0717-120">Die `My.Forms` -Objekt bietet Zugriff auf die Instanz des Hauptformulars der Anwendung, die beim Start erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a0717-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="a0717-121">Für alle anderen Formen der `My.Forms` -Objekt erstellt eine neue Instanz des Formulars auf, wenn darauf zugegriffen wird, und diese speichert.</span><span class="sxs-lookup"><span data-stu-id="a0717-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="a0717-122">Nachfolgende Versuche, diese Eigenschaft den Zugriff auf zurück diese Instanz des Formulars</span><span class="sxs-lookup"><span data-stu-id="a0717-122">Subsequent attempts to access that property return that instance of the form.</span></span>  
  
 <span data-ttu-id="a0717-123">Sie können durch Zuweisen eines Formulars dispose `Nothing` der Eigenschaft für dieses Formular.</span><span class="sxs-lookup"><span data-stu-id="a0717-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="a0717-124">Der Eigenschaftensetter Ruft die <xref:System.Windows.Forms.Form.Close%2A> -Methode der das Formular, und klicken Sie dann weist `Nothing` gespeicherten Wert.</span><span class="sxs-lookup"><span data-stu-id="a0717-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="a0717-125">Wenn Sie einen beliebigen Wert außer zuweisen `Nothing` löst der Setter der Eigenschaft ein <xref:System.ArgumentException> Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="a0717-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="a0717-126">Sie können testen, ob eine Eigenschaft der `My.Forms` Objekt wird eine Instanz des Formulars mithilfe der `Is` oder `IsNot` Operator.</span><span class="sxs-lookup"><span data-stu-id="a0717-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="a0717-127">Sie können diese Operatoren verwenden, um zu überprüfen, ob der Wert der Eigenschaft ist `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="a0717-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0717-128">In der Regel die `Is` oder `IsNot` Operator muss den Wert der Eigenschaft zum Ausführen des Vergleichs zu lesen.</span><span class="sxs-lookup"><span data-stu-id="a0717-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="a0717-129">Aber wenn die Eigenschaft derzeit speichert `Nothing`, die Eigenschaft erstellt eine neue Instanz des Formulars und dann diese Instanz zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a0717-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="a0717-130">Visual Basic-Compiler behandelt jedoch die Eigenschaften der `My.Forms` -Objekts auf andere Weise und ermöglicht die `Is` oder `IsNot` Operator, um den Status der Eigenschaft zu überprüfen, ohne Änderung ihres Werts.</span><span class="sxs-lookup"><span data-stu-id="a0717-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0717-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a0717-131">Example</span></span>  
 <span data-ttu-id="a0717-132">In diesem Beispiel wird der Titel der standardmäßigen `SidebarMenu` Formular.</span><span class="sxs-lookup"><span data-stu-id="a0717-132">This example changes the title of the default `SidebarMenu` form.</span></span>  
  
 [!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]  
  
 <span data-ttu-id="a0717-133">Für dieses Beispiel funktioniert, müssen Ihr Projekt ein Formular mit dem Namen `SidebarMenu`.</span><span class="sxs-lookup"><span data-stu-id="a0717-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>  
  
 <span data-ttu-id="a0717-134">Dieser Code funktioniert nur in einem Windows-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="a0717-134">This code will work only in a Windows Application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0717-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0717-135">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="a0717-136">Verfügbarkeit nach Projekttyp</span><span class="sxs-lookup"><span data-stu-id="a0717-136">Availability by Project Type</span></span>  
  
|<span data-ttu-id="a0717-137">Projekttyp:</span><span class="sxs-lookup"><span data-stu-id="a0717-137">Project type</span></span>|<span data-ttu-id="a0717-138">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="a0717-138">Available</span></span>|  
|---|---|  
|<span data-ttu-id="a0717-139">Windows-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a0717-139">Windows Application</span></span>|<span data-ttu-id="a0717-140">**Ja**</span><span class="sxs-lookup"><span data-stu-id="a0717-140">**Yes**</span></span>|  
|<span data-ttu-id="a0717-141">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="a0717-141">Class Library</span></span>|<span data-ttu-id="a0717-142">Nein</span><span class="sxs-lookup"><span data-stu-id="a0717-142">No</span></span>|  
|<span data-ttu-id="a0717-143">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="a0717-143">Console Application</span></span>|<span data-ttu-id="a0717-144">Nein</span><span class="sxs-lookup"><span data-stu-id="a0717-144">No</span></span>|  
|<span data-ttu-id="a0717-145">Windows-Steuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="a0717-145">Windows Control Library</span></span>|<span data-ttu-id="a0717-146">Nein</span><span class="sxs-lookup"><span data-stu-id="a0717-146">No</span></span>|  
|<span data-ttu-id="a0717-147">Websteuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="a0717-147">Web Control Library</span></span>|<span data-ttu-id="a0717-148">Nein</span><span class="sxs-lookup"><span data-stu-id="a0717-148">No</span></span>|  
|<span data-ttu-id="a0717-149">Windows-Dienst</span><span class="sxs-lookup"><span data-stu-id="a0717-149">Windows Service</span></span>|<span data-ttu-id="a0717-150">Nein</span><span class="sxs-lookup"><span data-stu-id="a0717-150">No</span></span>|  
|<span data-ttu-id="a0717-151">Website</span><span class="sxs-lookup"><span data-stu-id="a0717-151">Web Site</span></span>|<span data-ttu-id="a0717-152">Nein</span><span class="sxs-lookup"><span data-stu-id="a0717-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0717-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0717-153">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [<span data-ttu-id="a0717-154">Objekte</span><span class="sxs-lookup"><span data-stu-id="a0717-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)
- [<span data-ttu-id="a0717-155">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="a0717-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="a0717-156">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="a0717-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="a0717-157">Zugreifen auf Anwendungsformulare</span><span class="sxs-lookup"><span data-stu-id="a0717-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
