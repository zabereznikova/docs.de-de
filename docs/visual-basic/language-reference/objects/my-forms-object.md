---
title: My.Forms-Objekt
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fe548caacf2c8e7498e3b7abc814b4f89af9b3d6
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="myforms-object"></a><span data-ttu-id="007e0-102">My.Forms-Objekt</span><span class="sxs-lookup"><span data-stu-id="007e0-102">My.Forms Object</span></span>
<span data-ttu-id="007e0-103">Stellt Eigenschaften für den Zugriff auf eine Instanz jedes Windows Form, die im aktuellen Projekt deklariert.</span><span class="sxs-lookup"><span data-stu-id="007e0-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="007e0-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="007e0-104">Remarks</span></span>  
 <span data-ttu-id="007e0-105">Die `My.Forms` Objekt enthält eine Instanz von jeder Form im aktuellen Projekt.</span><span class="sxs-lookup"><span data-stu-id="007e0-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="007e0-106">Der Name der Eigenschaft ist identisch mit den Namen des Formulars, das die Eigenschaft zugreift.</span><span class="sxs-lookup"><span data-stu-id="007e0-106">The name of the property is the same as the name of the form that the property accesses.</span></span>   
  
 <span data-ttu-id="007e0-107">Sie können die bereitgestellten Formulare zugreifen, die `My.Forms` Objekt mit dem Namen des Formulars, ohne Qualifizierung.</span><span class="sxs-lookup"><span data-stu-id="007e0-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="007e0-108">Da der Eigenschaftsname des Formulars Typnamen identisch ist, können Sie diese auf einem Formular zugreifen, als ob es sich um eine Standardinstanz hatte.</span><span class="sxs-lookup"><span data-stu-id="007e0-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="007e0-109">`My.Forms.Form1.Show` entspricht beispielsweise `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="007e0-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>  
  
 <span data-ttu-id="007e0-110">Die `My.Forms` Objekt macht nur die Formulare, die das aktuelle Projekt zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="007e0-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="007e0-111">Es bietet keine auf Formulare im referenzierten DLLs deklariert.</span><span class="sxs-lookup"><span data-stu-id="007e0-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="007e0-112">Um ein Formular zuzugreifen, der eine DLL-Datei bereitstellt, müssen Sie den qualifizierten Namen des Formulars, geschrieben, wie Sie verwenden *DLL-Namen*. *Formularname*.</span><span class="sxs-lookup"><span data-stu-id="007e0-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>  
  
 <span data-ttu-id="007e0-113">Sie können die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> Eigenschaft, um eine Auflistung von offenen Formulare der Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="007e0-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>  
  
 <span data-ttu-id="007e0-114">Das Objekt und seine Eigenschaften sind nur für Windows-Anwendungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="007e0-114">The object and its properties are available only for Windows applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="007e0-115">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="007e0-115">Properties</span></span>  
 <span data-ttu-id="007e0-116">Jede Eigenschaft der `My.Forms` -Objekt bietet Zugriff auf eine Instanz eines Formulars im aktuellen Projekt.</span><span class="sxs-lookup"><span data-stu-id="007e0-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="007e0-117">Der Name der Eigenschaft ist identisch mit den Namen des Formulars, das die Eigenschaft zugreift, und der Eigenschaftentyp entspricht der Typ des Formulars.</span><span class="sxs-lookup"><span data-stu-id="007e0-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="007e0-118">Ist ein Konflikt von geschachteltem Klassennamen, der Name der Zugriff auf ein Formular ist *RootNamespace*_*Namespace*\_*Formularname*.</span><span class="sxs-lookup"><span data-stu-id="007e0-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="007e0-119">Betrachten Sie z. B. zwei Formulare mit dem Namen `Form1.`Wenn eines dieser Formulare im Stammnamespace ist `WindowsApplication1` und im Namespace `Namespace1`, würden Sie dieses Formular über zugreifen `My.Forms.WindowsApplication1_Namespace1_Form1`.</span><span class="sxs-lookup"><span data-stu-id="007e0-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>  
  
 <span data-ttu-id="007e0-120">Die `My.Forms` -Objekt bietet Zugriff auf die Instanz von Hauptformular der Anwendung, die beim Start erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="007e0-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="007e0-121">Für jede andere Form der `My.Forms` Objekt erstellt eine neue Instanz des Formulars aus, wenn er Zugriff auf und sie speichert.</span><span class="sxs-lookup"><span data-stu-id="007e0-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="007e0-122">Nachfolgende Versuche, die Zugriff auf diese Eigenschaft zurückgeben dieser Instanz des Formulars.</span><span class="sxs-lookup"><span data-stu-id="007e0-122">Subsequent attempts to access that property return that instance of the form.</span></span>  
  
 <span data-ttu-id="007e0-123">Sie können durch Zuweisen eines Formulars dispose `Nothing` für die Eigenschaft für das Formular.</span><span class="sxs-lookup"><span data-stu-id="007e0-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="007e0-124">Der Eigenschaftensetter Ruft die <xref:System.Windows.Forms.Form.Close%2A> -Methode des Formulars, und klicken Sie dann weist `Nothing` mit dem gespeicherten Wert.</span><span class="sxs-lookup"><span data-stu-id="007e0-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="007e0-125">Wenn Sie einen beliebigen Wert außer zuweisen `Nothing` der Eigenschaft Setter-Methode löst eine <xref:System.ArgumentException> Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="007e0-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="007e0-126">Sie können testen, ob eine Eigenschaft der `My.Forms` Objekt speichert eine Instanz des Formulars mit der `Is` oder `IsNot` Operator.</span><span class="sxs-lookup"><span data-stu-id="007e0-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="007e0-127">Sie können diese Operatoren verwenden, zum Überprüfen, ob der Wert der Eigenschaft ist `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="007e0-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="007e0-128">In der Regel die `Is` oder `IsNot` Operator muss den Wert der Eigenschaft zum Ausführen des Vergleichs zu lesen.</span><span class="sxs-lookup"><span data-stu-id="007e0-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="007e0-129">Jedoch, wenn die Eigenschaft aktuell speichert `Nothing`, die Eigenschaft erstellt eine neue Instanz des Formulars und gibt dann diese Instanz zurück.</span><span class="sxs-lookup"><span data-stu-id="007e0-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="007e0-130">Visual Basic-Compiler behandelt jedoch die Eigenschaften der `My.Forms` Objekt unterschiedlich, und ermöglicht die `Is` oder `IsNot` Operator, um den Status der Eigenschaft zu überprüfen, ohne den Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="007e0-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="007e0-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="007e0-131">Example</span></span>  
 <span data-ttu-id="007e0-132">In diesem Beispiel wird der Titel des Standardwerts `SidebarMenu` Formular.</span><span class="sxs-lookup"><span data-stu-id="007e0-132">This example changes the title of the default `SidebarMenu` form.</span></span>  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 <span data-ttu-id="007e0-133">Für dieses Beispiel funktioniert, muss das Projekt ein Formular mit dem Namen verfügen `SidebarMenu`.</span><span class="sxs-lookup"><span data-stu-id="007e0-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>  
  
 <span data-ttu-id="007e0-134">Dieser Code funktioniert nur in einem Windows-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="007e0-134">This code will work only in a Windows Application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="007e0-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="007e0-135">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="007e0-136">Verfügbarkeit nach Projekttyp</span><span class="sxs-lookup"><span data-stu-id="007e0-136">Availability by Project Type</span></span>  
  
|<span data-ttu-id="007e0-137">Projekttyp:</span><span class="sxs-lookup"><span data-stu-id="007e0-137">Project type</span></span>|<span data-ttu-id="007e0-138">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="007e0-138">Available</span></span>|  
|---|---|  
|<span data-ttu-id="007e0-139">Windows-Anwendung</span><span class="sxs-lookup"><span data-stu-id="007e0-139">Windows Application</span></span>|<span data-ttu-id="007e0-140">**Ja**</span><span class="sxs-lookup"><span data-stu-id="007e0-140">**Yes**</span></span>|  
|<span data-ttu-id="007e0-141">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="007e0-141">Class Library</span></span>|<span data-ttu-id="007e0-142">Nein</span><span class="sxs-lookup"><span data-stu-id="007e0-142">No</span></span>|  
|<span data-ttu-id="007e0-143">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="007e0-143">Console Application</span></span>|<span data-ttu-id="007e0-144">Nein</span><span class="sxs-lookup"><span data-stu-id="007e0-144">No</span></span>|  
|<span data-ttu-id="007e0-145">Windows-Steuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="007e0-145">Windows Control Library</span></span>|<span data-ttu-id="007e0-146">Nein</span><span class="sxs-lookup"><span data-stu-id="007e0-146">No</span></span>|  
|<span data-ttu-id="007e0-147">Websteuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="007e0-147">Web Control Library</span></span>|<span data-ttu-id="007e0-148">Nein</span><span class="sxs-lookup"><span data-stu-id="007e0-148">No</span></span>|  
|<span data-ttu-id="007e0-149">Windows-Dienst</span><span class="sxs-lookup"><span data-stu-id="007e0-149">Windows Service</span></span>|<span data-ttu-id="007e0-150">Nein</span><span class="sxs-lookup"><span data-stu-id="007e0-150">No</span></span>|  
|<span data-ttu-id="007e0-151">Website</span><span class="sxs-lookup"><span data-stu-id="007e0-151">Web Site</span></span>|<span data-ttu-id="007e0-152">Nein</span><span class="sxs-lookup"><span data-stu-id="007e0-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="007e0-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="007e0-153">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [<span data-ttu-id="007e0-154">Objekte</span><span class="sxs-lookup"><span data-stu-id="007e0-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)  
 [<span data-ttu-id="007e0-155">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="007e0-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="007e0-156">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="007e0-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="007e0-157">Zugreifen auf Anwendungsformulare</span><span class="sxs-lookup"><span data-stu-id="007e0-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
