---
title: Automatisch implementierte Eigenschaften
ms.date: 07/20/2015
f1_keywords:
- vb.AutoProperty
- vb.AutoImplementedProperty
helpviewer_keywords:
- properties [Visual Basic], auto-implemented
- auto-implemented properties [Visual Basic]
ms.assetid: 5c669f0b-cf95-4b4e-ae84-9cc55212ca87
ms.openlocfilehash: f50b1f40ef9843391c6622561bfd8a8eaae6fc17
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090053"
---
# <a name="auto-implemented-properties-visual-basic"></a><span data-ttu-id="972dc-102">Automatisch implementierte Eigenschaften (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="972dc-102">Auto-Implemented Properties (Visual Basic)</span></span>

<span data-ttu-id="972dc-103">*Automatisch implementierte Eigenschaften* ermöglichen es Ihnen, schnell eine Eigenschaft einer Klasse anzugeben, ohne Code in `Get` und die-Eigenschaft schreiben zu müssen `Set` .</span><span class="sxs-lookup"><span data-stu-id="972dc-103">*Auto-implemented properties* enable you to quickly specify a property of a class without having to write code to `Get` and `Set` the property.</span></span> <span data-ttu-id="972dc-104">Wenn Sie Code für eine automatisch implementierte Eigenschaft schreiben, erstellt der Visual Basic-Compiler automatisch ein privates Feld zum Speichern der Eigenschaftsvariablen zusätzlich zum Erstellen der zugeordneten `Get` und `Set` Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="972dc-104">When you write code for an auto-implemented property, the Visual Basic compiler automatically creates a private field to store the property variable in addition to creating the associated `Get` and `Set` procedures.</span></span>  
  
 <span data-ttu-id="972dc-105">Mit automatisch implementierten Eigenschaften kann eine Eigenschaft, einschließlich eines Standardwerts, in einer einzelnen Zeile deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="972dc-105">With auto-implemented properties, a property, including a default value, can be declared in a single line.</span></span> <span data-ttu-id="972dc-106">Im folgenden Beispiel werden drei Eigenschaftendeklarationen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="972dc-106">The following example shows three property declarations.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#1)]  
  
 <span data-ttu-id="972dc-107">Eine automatisch implementierte Eigenschaft entspricht einer Eigenschaft, deren Eigenschaftswert in einem privaten Feld gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="972dc-107">An auto-implemented property is equivalent to a property for which the property value is stored in a private field.</span></span> <span data-ttu-id="972dc-108">Im folgenden Codebeispiel wird eine automatisch implementierte Eigenschaft veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="972dc-108">The following code example shows an auto-implemented property.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#5)]  
  
 <span data-ttu-id="972dc-109">Im folgenden Codebeispiel wird der entsprechende Code für das vorherige Beispiel der automatisch implementierten Eigenschaft veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="972dc-109">The following code example shows the equivalent code for the previous auto-implemented property example.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#2)]  
  
 <span data-ttu-id="972dc-110">Der folgende Code veranschaulicht die Implementierung von Readonly-Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="972dc-110">The following code show implementing readonly properties:</span></span>  
  
```vb  
Class Customer  
   Public ReadOnly Property Tags As New List(Of String)  
   Public ReadOnly Property Name As String = ""  
   Public ReadOnly Property File As String  
  
   Sub New(file As String)  
      Me.File = file  
   End Sub  
End Class  
```  
  
 <span data-ttu-id="972dc-111">Sie können die Eigenschaft mit Initialisierungsausdrücken zuweisen, wie im Beispiel gezeigt, oder Sie können die Eigenschaften im Konstruktor des enthaltenden Typs zuweisen.</span><span class="sxs-lookup"><span data-stu-id="972dc-111">You can assign to the property with initialization expressions as shown in the example, or you can assign to the properties in the containing type’s constructor.</span></span>  <span data-ttu-id="972dc-112">Sie können jederzeit auf die dahinter liegenden Felder der Readonly-Eigenschaften zuweisen.</span><span class="sxs-lookup"><span data-stu-id="972dc-112">You can assign to the backing fields of readonly properties at any time.</span></span>  
  
## <a name="backing-field"></a><span data-ttu-id="972dc-113">Dahinter liegendes Feld</span><span class="sxs-lookup"><span data-stu-id="972dc-113">Backing Field</span></span>  

 <span data-ttu-id="972dc-114">Wenn Sie eine automatisch implementierte Eigenschaft deklarieren, erstellt Visual Basic automatisch ein verborgenes privates Feld, das als dahinter liegendes *Feld* bezeichnet wird und den Eigenschafts Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="972dc-114">When you declare an auto-implemented property, Visual Basic automatically creates a hidden private field called the *backing field* to contain the property value.</span></span> <span data-ttu-id="972dc-115">Der dahinter liegende Feldname ist die automatisch implementierte Eigenschaft mit einem vorangestellten Unterstrich (_).</span><span class="sxs-lookup"><span data-stu-id="972dc-115">The backing field name is the auto-implemented property name preceded by an underscore (_).</span></span> <span data-ttu-id="972dc-116">Angenommen, Sie deklarieren eine automatisch implementierte Eigenschaft mit dem Namen `ID`, dann heißt das dahinter liegende Feld `_ID`.</span><span class="sxs-lookup"><span data-stu-id="972dc-116">For example, if you declare an auto-implemented property named `ID`, the backing field is named `_ID`.</span></span> <span data-ttu-id="972dc-117">Wenn Sie ein Member der Klasse mit einschließen, das ebenfalls den Namen `_ID` trägt, erzeugen Sie einen Namenskonflikt und Visual Basic meldet einen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="972dc-117">If you include a member of your class that is also named `_ID`, you produce a naming conflict and Visual Basic reports a compiler error.</span></span>  
  
 <span data-ttu-id="972dc-118">Das dahinter liegende Feld verfügt ebenfalls über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="972dc-118">The backing field also has the following characteristics:</span></span>  
  
- <span data-ttu-id="972dc-119">Der Zugriffsmodifizierer für das dahinter liegende Feld ist immer `Private`, selbst wenn die Eigenschaft selbst über eine andere Zugriffsebene verfügt, z. B `Public`.</span><span class="sxs-lookup"><span data-stu-id="972dc-119">The access modifier for the backing field is always `Private`, even when the property itself has a different access level, such as `Public`.</span></span>  
  
- <span data-ttu-id="972dc-120">Wenn die Eigenschaft als `Shared` markiert ist, wird das dahinter liegende Feld auch freigegeben.</span><span class="sxs-lookup"><span data-stu-id="972dc-120">If the property is marked as `Shared`, the backing field also is shared.</span></span>  
  
- <span data-ttu-id="972dc-121">Für die Eigenschaft angegebene Attribute gelten nicht für das dahinter liegende Feld.</span><span class="sxs-lookup"><span data-stu-id="972dc-121">Attributes specified for the property do not apply to the backing field.</span></span>  
  
- <span data-ttu-id="972dc-122">Auf das dahinter liegende Feld kann durch Code innerhalb der Klasse und von Debugtools, wie dem Überwachungsfenster, zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="972dc-122">The backing field can be accessed from code within the class and from debugging tools such as the Watch window.</span></span> <span data-ttu-id="972dc-123">Das dahinter liegende Feld wird jedoch nicht in einer IntelliSense-Vervollständigungsliste für Word angezeigt.</span><span class="sxs-lookup"><span data-stu-id="972dc-123">However, the backing field does not show in an IntelliSense word completion list.</span></span>  
  
## <a name="initializing-an-auto-implemented-property"></a><span data-ttu-id="972dc-124">So definieren Sie eine automatisch implementierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="972dc-124">Initializing an Auto-Implemented Property</span></span>  

 <span data-ttu-id="972dc-125">Jeder Ausdruck, der verwendet werden kann, um ein Feld zu initialisieren, ist gültig für die Initialisierung einer automatisch implementierte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="972dc-125">Any expression that can be used to initialize a field is valid for initializing an auto-implemented property.</span></span> <span data-ttu-id="972dc-126">Wenn Sie eine automatisch implementierte Eigenschaft initialisieren, wird der Ausdruck ausgewertet und der `Set` Prozedur für die Eigenschaft übergeben.</span><span class="sxs-lookup"><span data-stu-id="972dc-126">When you initialize an auto-implemented property, the expression is evaluated and passed to the `Set` procedure for the property.</span></span> <span data-ttu-id="972dc-127">Die folgenden Codebeispiele zeigen einige automatisch implementierte Eigenschaften, die Anfangswerte enthalten.</span><span class="sxs-lookup"><span data-stu-id="972dc-127">The following code examples show some auto-implemented properties that include initial values.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#3)]  
  
 <span data-ttu-id="972dc-128">Sie können eine automatisch implementierte Eigenschaft nicht initialisieren, wenn sie ein Member von `Interface` oder `MustOverride` gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="972dc-128">You cannot initialize an auto-implemented property that is a member of an `Interface`, or one that is marked `MustOverride`.</span></span>  
  
 <span data-ttu-id="972dc-129">Wenn Sie eine automatisch implementierte Eigenschaft als Member von `Structure` deklarieren, dann können Sie nur dann die automatisch implementierte Eigenschaft initialisieren, wenn sie als `Shared` gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="972dc-129">When you declare an auto-implemented property as a member of a `Structure`, you can only initialize the auto-implemented property if it is marked as `Shared`.</span></span>  
  
 <span data-ttu-id="972dc-130">Wenn Sie eine automatisch implementierte Eigenschaft als Array deklarieren, können keine expliziten Arraygrenzen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="972dc-130">When you declare an auto-implemented property as an array, you cannot specify explicit array bounds.</span></span> <span data-ttu-id="972dc-131">Allerdings können Sie einen Wert mit einem Arrayinitialisierer angeben, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="972dc-131">However, you can supply a value by using an array initializer, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#4)]  
  
## <a name="property-definitions-that-require-standard-syntax"></a><span data-ttu-id="972dc-132">Eigenschaftendefinitionen, die Standardsyntax erfordern</span><span class="sxs-lookup"><span data-stu-id="972dc-132">Property Definitions That Require Standard Syntax</span></span>  

 <span data-ttu-id="972dc-133">Automatisch implementierte Eigenschaften sind praktisch und unterstützen viele Programmierszenarien.</span><span class="sxs-lookup"><span data-stu-id="972dc-133">Auto-implemented properties are convenient and support many programming scenarios.</span></span> <span data-ttu-id="972dc-134">Es gibt jedoch Situationen, in denen eine automatisch implementierte Eigenschaft nicht verwendet werden kann und stattdessen die standardmäßige oder *Erweiterte*Eigenschafts Syntax verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="972dc-134">However, there are situations in which you cannot use an auto-implemented property and must instead use standard, or *expanded*, property syntax.</span></span>  
  
 <span data-ttu-id="972dc-135">In diesem Fall müssen Sie eine erweiterte Eigenschaftsdefinition-Syntax verwenden, wenn Sie eine der folgenden durchführen möchten:</span><span class="sxs-lookup"><span data-stu-id="972dc-135">You have to use expanded property-definition syntax if you want to do any one of the following:</span></span>  
  
- <span data-ttu-id="972dc-136">Hinzufügen von Code für die Prozedur `Get` oder `Set` einer Eigenschaft, z. B. Code zum Überprüfen eingehender Werte in der Prozedur `Set`.</span><span class="sxs-lookup"><span data-stu-id="972dc-136">Add code to the `Get` or `Set` procedure of a property, such as code to validate incoming values in the `Set` procedure.</span></span> <span data-ttu-id="972dc-137">Sie möchten z. B. überprüfen, ob eine Zeichenfolge, die eine Telefonnummer darstellt, die erforderliche Anzahl von Ziffern enthält, bevor der Eigenschaftswert festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="972dc-137">For example, you might want to verify that a string that represents a telephone number contains the required number of numerals before setting the property value.</span></span>  
  
- <span data-ttu-id="972dc-138">Angeben unterschiedlicher Zugriffsmöglichkeiten für die Prozeduren `Get` und `Set`.</span><span class="sxs-lookup"><span data-stu-id="972dc-138">Specify different accessibility for the `Get` and `Set` procedure.</span></span> <span data-ttu-id="972dc-139">Sie möchten z. B. die `Set` Prozedur `Private` und die `Get` Prozedur `Public` erstellen.</span><span class="sxs-lookup"><span data-stu-id="972dc-139">For example, you might want to make the `Set` procedure `Private` and the `Get` procedure `Public`.</span></span>  
  
- <span data-ttu-id="972dc-140">Erstellen von Eigenschaften mit `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="972dc-140">Create properties that are `WriteOnly`.</span></span>  
  
- <span data-ttu-id="972dc-141">Verwenden von parametrisierten Eigenschaften (einschließlich `Default` Eigenschaften).</span><span class="sxs-lookup"><span data-stu-id="972dc-141">Use parameterized properties (including `Default` properties).</span></span> <span data-ttu-id="972dc-142">Sie müssen eine erweiterte Eigenschaft deklarieren, um einen Parameter für die Eigenschaft oder zusätzliche Parameter für die `Set` Prozedur zu spezifizieren.</span><span class="sxs-lookup"><span data-stu-id="972dc-142">You must declare an expanded property in order to specify a parameter for the property, or to specify additional parameters for the `Set` procedure.</span></span>  
  
- <span data-ttu-id="972dc-143">Platzieren Sie ein Attribut für das dahinter liegende Feld oder ändern Sie die Zugriffsebene des dahinter liegenden Felds.</span><span class="sxs-lookup"><span data-stu-id="972dc-143">Place an attribute on the backing field, or change the access level of the backing field.</span></span>  
  
- <span data-ttu-id="972dc-144">Geben Sie XML-Kommentaren für das dahinter liegende Feld an.</span><span class="sxs-lookup"><span data-stu-id="972dc-144">Provide XML comments for the backing field.</span></span>  
  
## <a name="expanding-an-auto-implemented-property"></a><span data-ttu-id="972dc-145">So erweitern Sie eine automatisch implementierte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="972dc-145">Expanding an Auto-Implemented Property</span></span>  

 <span data-ttu-id="972dc-146">Wenn Sie eine automatisch implementierte Eigenschaft zu einer erweiterten Eigenschaft konvertieren müssen, die eine `Get` oder `Set` Prozedur enthält, dann kann der Visual Basic-Code-Editor automatisch die `Get` und `Set` Prozeduren und `End Property` -Anweisung für die Eigenschaft generieren.</span><span class="sxs-lookup"><span data-stu-id="972dc-146">If you have to convert an auto-implemented property to an expanded property that contains a `Get` or `Set` procedure, the Visual Basic Code Editor can automatically generate the `Get` and `Set` procedures and `End Property` statement for the property.</span></span> <span data-ttu-id="972dc-147">Der Code wird generiert, wenn Sie den Cursor in einer leeren Zeile nach der `Property` Anweisung platzieren, eine `G` (für `Get` ) oder eine `S` (für `Set` ) eingeben und die EINGABETASTE drücken.</span><span class="sxs-lookup"><span data-stu-id="972dc-147">The code is generated if you put the cursor on a blank line following the `Property` statement, type a `G` (for `Get`) or an `S` (for `Set`) and press ENTER.</span></span> <span data-ttu-id="972dc-148">Der Visual Basic-Code-Editor generiert automatisch `Get` oder `Set` für schreibgeschützte und lesegeschützte Eigenschaften beim Drücken der EINGABETASTE am Ende der Prozedur eine `Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="972dc-148">The Visual Basic Code Editor automatically generates the `Get` or `Set` procedure for read-only and write-only properties when you press ENTER at the end of a `Property` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="972dc-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="972dc-149">See also</span></span>

- [<span data-ttu-id="972dc-150">Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="972dc-150">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="972dc-151">Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="972dc-151">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="972dc-152">Property Statement</span><span class="sxs-lookup"><span data-stu-id="972dc-152">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="972dc-153">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="972dc-153">ReadOnly</span></span>](../../../language-reference/modifiers/readonly.md)
- [<span data-ttu-id="972dc-154">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="972dc-154">WriteOnly</span></span>](../../../language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="972dc-155">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="972dc-155">Objects and Classes</span></span>](../objects-and-classes/index.md)
