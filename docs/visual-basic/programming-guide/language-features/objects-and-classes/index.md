---
title: Objekte und Klassen
ms.date: 05/26/2020
helpviewer_keywords:
- classes [Visual Basic]
- objects [Visual Basic]
ms.assetid: c68c5752-1006-46e1-975a-6717b62a42fc
ms.openlocfilehash: 9e3cf262ef617a1ae5ee92bcc3d6fd5c691602f9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600412"
---
# <a name="objects-and-classes-in-visual-basic"></a><span data-ttu-id="67c20-102">Objekte und Klassen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67c20-102">Objects and classes in Visual Basic</span></span>

<span data-ttu-id="67c20-103">Ein *Objekt* ist eine Kombination aus Code und Daten, die als Einheit behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="67c20-103">An *object* is a combination of code and data that can be treated as a unit.</span></span> <span data-ttu-id="67c20-104">Ein Objekt kann ein Teil einer Anwendung sein wie ein Steuerelement oder ein Formular.</span><span class="sxs-lookup"><span data-stu-id="67c20-104">An object can be a piece of an application, like a control or a form.</span></span> <span data-ttu-id="67c20-105">Eine vollständige Anwendung kann auch ein Objekt sein.</span><span class="sxs-lookup"><span data-stu-id="67c20-105">An entire application can also be an object.</span></span>

<span data-ttu-id="67c20-106">Wenn Sie eine Anwendung in Visual Basic erstellen, arbeiten Sie ständig mit-Objekten.</span><span class="sxs-lookup"><span data-stu-id="67c20-106">When you create an application in Visual Basic, you constantly work with objects.</span></span> <span data-ttu-id="67c20-107">Sie können Objekte verwenden, die von Visual Basic bereitgestellt werden, z. b. Steuerelemente, Formulare und Datenzugriffs Objekte.</span><span class="sxs-lookup"><span data-stu-id="67c20-107">You can use objects provided by Visual Basic, such as controls, forms, and data access objects.</span></span> <span data-ttu-id="67c20-108">Sie können auch Objekte aus anderen Anwendungen in Ihrer Visual Basic Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="67c20-108">You can also use objects from other applications within your Visual Basic application.</span></span> <span data-ttu-id="67c20-109">Sie können sogar eigene Objekte erstellen und für diese zusätzliche Eigenschaften und Methoden definieren.</span><span class="sxs-lookup"><span data-stu-id="67c20-109">You can even create your own objects and define additional properties and methods for them.</span></span> <span data-ttu-id="67c20-110">Objekte verhalten sich wie vorgefertigte Bausteine für Programme – Sie können ein Stück Code einmal schreiben und immer wieder verwenden.</span><span class="sxs-lookup"><span data-stu-id="67c20-110">Objects act like prefabricated building blocks for programs — they let you write a piece of code once and reuse it over and over.</span></span>

<span data-ttu-id="67c20-111">Dieses Thema beschreibt Objekte im Detail.</span><span class="sxs-lookup"><span data-stu-id="67c20-111">This topic discusses objects in detail.</span></span>

## <a name="objects-and-classes"></a><span data-ttu-id="67c20-112">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="67c20-112">Objects and classes</span></span>

<span data-ttu-id="67c20-113">Jedes Objekt in Visual Basic wird von einer *Klasse*definiert.</span><span class="sxs-lookup"><span data-stu-id="67c20-113">Each object in Visual Basic is defined by a *class*.</span></span> <span data-ttu-id="67c20-114">Eine Klasse beschreibt die Variablen, Eigenschaften, Prozeduren und Ereignisse eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="67c20-114">A class describes the variables, properties, procedures, and events of an object.</span></span> <span data-ttu-id="67c20-115">Objekte sind Instanzen von Klassen. Sie können beliebig viele Objekte erstellen, die Sie benötigen, sobald Sie eine Klasse definiert haben.</span><span class="sxs-lookup"><span data-stu-id="67c20-115">Objects are instances of classes; you can create as many objects you need once you have defined a class.</span></span>

<span data-ttu-id="67c20-116">Um die Beziehung zwischen einem Objekt und seiner Klasse zu verstehen, stellen Sie sich Ausstechformen und Kekse vor.</span><span class="sxs-lookup"><span data-stu-id="67c20-116">To understand the relationship between an object and its class, think of cookie cutters and cookies.</span></span> <span data-ttu-id="67c20-117">Die Ausstechform ist die Klasse.</span><span class="sxs-lookup"><span data-stu-id="67c20-117">The cookie cutter is the class.</span></span> <span data-ttu-id="67c20-118">Sie definiert die Merkmale der einzelnen Kekse, z.B. die Größe und Form.</span><span class="sxs-lookup"><span data-stu-id="67c20-118">It defines the characteristics of each cookie, for example size and shape.</span></span> <span data-ttu-id="67c20-119">Die Klasse wird verwendet, um Objekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="67c20-119">The class is used to create objects.</span></span> <span data-ttu-id="67c20-120">Die Objekte sind die Kekse.</span><span class="sxs-lookup"><span data-stu-id="67c20-120">The objects are the cookies.</span></span>

<span data-ttu-id="67c20-121">Sie müssen ein-Objekt erstellen, bevor Sie auf seine Member zugreifen können, mit Ausnahme von Membern, auf [`Shared`](../../../language-reference/modifiers/shared.md) die ohne ein Objekt der-Klasse zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="67c20-121">You must create an object before you can access its members, except for [`Shared`](../../../language-reference/modifiers/shared.md) members which can be accessed without an object of the class.</span></span>

### <a name="create-an-object-from-a-class"></a><span data-ttu-id="67c20-122">Erstellen eines Objekts aus einer Klasse</span><span class="sxs-lookup"><span data-stu-id="67c20-122">Create an object from a class</span></span>

1. <span data-ttu-id="67c20-123">Bestimmen Sie, von welcher Klasse Sie ein Objekt erstellen möchten, oder definieren Sie eine eigene Klasse.</span><span class="sxs-lookup"><span data-stu-id="67c20-123">Determine from which class you want to create an object, or define your own class.</span></span> <span data-ttu-id="67c20-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="67c20-124">For example:</span></span>

   ```vb
   Public Class Customer
       Public Property AccountNumber As Integer
   End Class
   ```

2. <span data-ttu-id="67c20-125">Schreiben Sie eine [Dim-Anweisung](../../../language-reference/statements/dim-statement.md), um eine Variable zu erstellen, der Sie eine Klasseninstanz zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="67c20-125">Write a [Dim Statement](../../../language-reference/statements/dim-statement.md) to create a variable to which you can assign a class instance.</span></span> <span data-ttu-id="67c20-126">Die Variable sollte vom Typ der gewünschten Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="67c20-126">The variable should be of the type of the desired class.</span></span>

   ```vb
   Dim nextCustomer As Customer
   ```

3. <span data-ttu-id="67c20-127">Fügen Sie das Schlüsselwort [Neuer Operator](../../../language-reference/operators/new-operator.md) hinzu, um die Variable für eine neue Instanz der Klasse zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="67c20-127">Add the [New Operator](../../../language-reference/operators/new-operator.md) keyword to initialize the variable to a new instance of the class.</span></span>

   ```vb
   Dim nextCustomer As New Customer
   ```

4. <span data-ttu-id="67c20-128">Sie können jetzt die Member der Klasse über die Objektvariable aufrufen.</span><span class="sxs-lookup"><span data-stu-id="67c20-128">You can now access the members of the class through the object variable.</span></span>

   ```vb
   nextCustomer.AccountNumber = lastAccountNumber + 1
   ```

> [!NOTE]
> <span data-ttu-id="67c20-129">Sie sollten die Variable möglichst so deklarieren, dass sie den Klassentyp aufweist, den Sie ihr zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="67c20-129">Whenever possible, you should declare the variable to be of the class type you intend to assign to it.</span></span> <span data-ttu-id="67c20-130">Dies wird als *frühe Bindung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="67c20-130">This is called *early binding*.</span></span> <span data-ttu-id="67c20-131">Wenn Sie den Klassentyp zur Kompilierungszeit nicht kennen, können Sie *Späte Bindung* aufrufen, indem Sie für die Variable den [Objekt-Datentyp](../../../language-reference/data-types/object-data-type.md) deklarieren.</span><span class="sxs-lookup"><span data-stu-id="67c20-131">If you don't know the class type at compile time, you can invoke *late binding* by declaring the variable to be of the [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="67c20-132">Allerdings kann die späte Bindung zu Leistungseinbußen und Einschränkungen des Zugriffs auf die Member des Laufzeitobjekts führen.</span><span class="sxs-lookup"><span data-stu-id="67c20-132">However, late binding can make performance slower and limit access to the run-time object's members.</span></span> <span data-ttu-id="67c20-133">Weitere Informationen finden Sie unter [Object Variable Declaration](../variables/object-variable-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="67c20-133">For more information, see [Object Variable Declaration](../variables/object-variable-declaration.md).</span></span>

### <a name="multiple-instances"></a><span data-ttu-id="67c20-134">Mehrfache Instanzen</span><span class="sxs-lookup"><span data-stu-id="67c20-134">Multiple instances</span></span>

<span data-ttu-id="67c20-135">Neu erstellte Objekte aus einer Klasse sind häufig identisch.</span><span class="sxs-lookup"><span data-stu-id="67c20-135">Objects newly created from a class are often identical to each other.</span></span> <span data-ttu-id="67c20-136">Sobald sie als einzelne Objekte vorhanden sind, können jedoch ihre Variablen und Eigenschaften unabhängig von den anderen Instanzen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="67c20-136">Once they exist as individual objects, however, their variables and properties can be changed independently of the other instances.</span></span> <span data-ttu-id="67c20-137">Beispiel: Wenn Sie drei Kontrollkästchen zu einem Formular hinzufügen, ist jedes Kontrollkästchenobjekt eine Instanz der Klasse <xref:System.Windows.Forms.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="67c20-137">For example, if you add three check boxes to a form, each check box object is an instance of the <xref:System.Windows.Forms.CheckBox> class.</span></span> <span data-ttu-id="67c20-138">Die einzelnen <xref:System.Windows.Forms.CheckBox>-Objekte verfügen über einen gemeinsamen Satz von Merkmalen und Funktionen (Eigenschaften, Variablen, Prozeduren und Ereignisse), die anhand der Klasse definiert sind.</span><span class="sxs-lookup"><span data-stu-id="67c20-138">The individual <xref:System.Windows.Forms.CheckBox> objects share a common set of characteristics and capabilities (properties, variables, procedures, and events) defined by the class.</span></span> <span data-ttu-id="67c20-139">Alle verfügen jedoch über einen eigenen Namen, können separat aktiviert und deaktiviert sowie an einer anderen Stelle im Formular platziert werden.</span><span class="sxs-lookup"><span data-stu-id="67c20-139">However, each has its own name, can be separately enabled and disabled, and can be placed in a different location on the form.</span></span>

## <a name="object-members"></a><span data-ttu-id="67c20-140">Objektmember</span><span class="sxs-lookup"><span data-stu-id="67c20-140">Object members</span></span>

<span data-ttu-id="67c20-141">Ein Objekt ist ein Element einer Anwendung, das eine *Instanz* einer Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="67c20-141">An object is an element of an application, representing an *instance* of a class.</span></span> <span data-ttu-id="67c20-142">Felder, Eigenschaften, Methoden und Ereignisse sind die Bausteine von Objekten und bilden ihre *Member*.</span><span class="sxs-lookup"><span data-stu-id="67c20-142">Fields, properties, methods, and events are the building blocks of objects and constitute their *members*.</span></span>

### <a name="member-access"></a><span data-ttu-id="67c20-143">Memberzugriff</span><span class="sxs-lookup"><span data-stu-id="67c20-143">Member Access</span></span>

<span data-ttu-id="67c20-144">Sie greifen auf einen Member eines Objekts zu, indem Sie nacheinander den Namen der Objektvariablen, einen Zeitraum (`.`) und den Namen des Members angeben.</span><span class="sxs-lookup"><span data-stu-id="67c20-144">You access a member of an object by specifying, in order, the name of the object variable, a period (`.`), and the name of the member.</span></span> <span data-ttu-id="67c20-145">Im folgenden Beispiel wird die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft eines <xref:System.Windows.Forms.Label>-Objekts festgelegt.</span><span class="sxs-lookup"><span data-stu-id="67c20-145">The following example sets the <xref:System.Windows.Forms.Control.Text%2A> property of a <xref:System.Windows.Forms.Label> object.</span></span>

```vb
warningLabel.Text = "Data not saved"
```

#### <a name="intellisense-listing-of-members"></a><span data-ttu-id="67c20-146">IntelliSense-Auflistung von Membern</span><span class="sxs-lookup"><span data-stu-id="67c20-146">IntelliSense listing of members</span></span>

<span data-ttu-id="67c20-147">IntelliSense listet die Member einer Klasse auf, wenn Sie die Option „Member auflisten“ aufrufen, beispielsweise wenn Sie einen Punkt (`.`) als Memberzugriffsoperator eingeben.</span><span class="sxs-lookup"><span data-stu-id="67c20-147">IntelliSense lists members of a class when you invoke its List Members option, for example when you type a period (`.`) as a member-access operator.</span></span> <span data-ttu-id="67c20-148">Wenn Sie den Punkt nach dem Namen einer Variablen eingeben, die als Instanz dieser Klasse deklariert war, listet IntelliSense alle Instanzmember und keinen der freigegebenen Member auf.</span><span class="sxs-lookup"><span data-stu-id="67c20-148">If you type the period following the name of a variable declared as an instance of that class, IntelliSense lists all the instance members and none of the shared members.</span></span> <span data-ttu-id="67c20-149">Wenn Sie den Punkt nach dem Klassennamen selbst eingeben, listet IntelliSense alle freigegebenen Member und keinen der Instanzmember auf.</span><span class="sxs-lookup"><span data-stu-id="67c20-149">If you type the period following the class name itself, IntelliSense lists all the shared members and none of the instance members.</span></span> <span data-ttu-id="67c20-150">Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense).</span><span class="sxs-lookup"><span data-stu-id="67c20-150">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>

### <a name="fields-and-properties"></a><span data-ttu-id="67c20-151">Felder und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="67c20-151">Fields and properties</span></span>

<span data-ttu-id="67c20-152">*Felder* und *Eigenschaften* stellen die in einem Objekt enthaltenen Informationen dar.</span><span class="sxs-lookup"><span data-stu-id="67c20-152">*Fields* and *properties* represent information stored in an object.</span></span> <span data-ttu-id="67c20-153">Sie rufen ihre Werte ab und legen diese mit Zuweisungsanweisungen ebenso fest, wie Sie lokale Variablen in einer Prozedur abrufen und festlegen.</span><span class="sxs-lookup"><span data-stu-id="67c20-153">You retrieve and set their values with assignment statements the same way you retrieve and set local variables in a procedure.</span></span> <span data-ttu-id="67c20-154">Das folgende Beispiel ruft die <xref:System.Windows.Forms.Control.Width%2A>-Eigenschaft ab und legt die <xref:System.Windows.Forms.Control.ForeColor%2A>-Eigenschaft eines <xref:System.Windows.Forms.Label>-Objekts fest.</span><span class="sxs-lookup"><span data-stu-id="67c20-154">The following example retrieves the <xref:System.Windows.Forms.Control.Width%2A> property and sets the <xref:System.Windows.Forms.Control.ForeColor%2A> property of a <xref:System.Windows.Forms.Label> object.</span></span>

```vb
Dim warningWidth As Integer = warningLabel.Width
warningLabel.ForeColor = System.Drawing.Color.Red
```

<span data-ttu-id="67c20-155">Beachten Sie, dass ein Feld auch als *Membervariable* bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="67c20-155">Note that a field is also called a *member variable*.</span></span>

<span data-ttu-id="67c20-156">Verwenden Sie Eigenschaftenprozeduren in folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="67c20-156">Use property procedures when:</span></span>

- <span data-ttu-id="67c20-157">Sie müssen steuern, wann und wie ein Wert festgelegt oder abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="67c20-157">You need to control when and how a value is set or retrieved.</span></span>

- <span data-ttu-id="67c20-158">Die Eigenschaft weist einen genau definierten Satz von Werten auf, die überprüft werden müssen.</span><span class="sxs-lookup"><span data-stu-id="67c20-158">The property has a well-defined set of values that need to be validated.</span></span>

- <span data-ttu-id="67c20-159">Das Festlegen des Werts führt zu einer wahrnehmbaren Änderung am Zustand des Objekts, z.B. einer `IsVisible`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="67c20-159">Setting the value causes some perceptible change in the object's state, such as an `IsVisible` property.</span></span>

- <span data-ttu-id="67c20-160">Das Festlegen der Eigenschaft führt zu Änderungen an anderen internen Variablen oder den Werten anderer Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="67c20-160">Setting the property causes changes to other internal variables or to the values of other properties.</span></span>

- <span data-ttu-id="67c20-161">Eine Reihe von Schritten muss ausgeführt werden, bevor die Eigenschaft festgelegt oder abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="67c20-161">A set of steps must be performed before the property can be set or retrieved.</span></span>

<span data-ttu-id="67c20-162">Verwenden Sie Felder in folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="67c20-162">Use fields when:</span></span>

- <span data-ttu-id="67c20-163">Der Wert ist der eines sich selbst überprüfenden Typs.</span><span class="sxs-lookup"><span data-stu-id="67c20-163">The value is of a self-validating type.</span></span> <span data-ttu-id="67c20-164">Beispiel: Ein Fehler oder die automatische Datenkonvertierung erfolgt, wenn ein anderer Wert als `True` oder `False` einer `Boolean`-Variable zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="67c20-164">For example, an error or automatic data conversion occurs if a value other than `True` or `False` is assigned to a `Boolean` variable.</span></span>

- <span data-ttu-id="67c20-165">Jeder Wert im vom Datentyp unterstützten Bereich ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="67c20-165">Any value in the range supported by the data type is valid.</span></span> <span data-ttu-id="67c20-166">Dies gilt für zahlreiche Eigenschaften vom Typ `Single` oder `Double`.</span><span class="sxs-lookup"><span data-stu-id="67c20-166">This is true of many properties of type `Single` or `Double`.</span></span>

- <span data-ttu-id="67c20-167">Die Eigenschaft ist ein `String`-Datentyp, und es gibt keine Einschränkung für die Größe oder den Wert der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="67c20-167">The property is a `String` data type, and there is no constraint on the size or value of the string.</span></span>

- <span data-ttu-id="67c20-168">Weitere Informationen finden Sie unter [Property Procedures](../procedures/property-procedures.md) (Eigenschaftenprozeduren).</span><span class="sxs-lookup"><span data-stu-id="67c20-168">For more information, see [Property Procedures](../procedures/property-procedures.md).</span></span>

> [!TIP]
> <span data-ttu-id="67c20-169">Behalten Sie immer die nicht konstanten Felder privat.</span><span class="sxs-lookup"><span data-stu-id="67c20-169">Always keep the non-constant fields private.</span></span> <span data-ttu-id="67c20-170">Wenn Sie es als öffentlich festlegen möchten, verwenden Sie stattdessen eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="67c20-170">When you want to make it public, use a property instead.</span></span>

### <a name="methods"></a><span data-ttu-id="67c20-171">Methoden</span><span class="sxs-lookup"><span data-stu-id="67c20-171">Methods</span></span>

<span data-ttu-id="67c20-172">Eine *Methode* ist eine Aktion, die von einem Objekt ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="67c20-172">A *method* is an action that an object can perform.</span></span> <span data-ttu-id="67c20-173">Beispielsweise ist <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A> eine Methode des <xref:System.Windows.Forms.ComboBox>-Objekts, die einen neuen Eintrag zu einem Kombinationsfeld hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="67c20-173">For example, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A> is a method of the <xref:System.Windows.Forms.ComboBox> object that adds a new entry to a combo box.</span></span>

<span data-ttu-id="67c20-174">Im folgenden Beispiel wird die Verwendung der <xref:System.Windows.Forms.Timer.Start%2A>-Methode eines <xref:System.Windows.Forms.Timer>-Objekts gezeigt.</span><span class="sxs-lookup"><span data-stu-id="67c20-174">The following example demonstrates the <xref:System.Windows.Forms.Timer.Start%2A> method of a <xref:System.Windows.Forms.Timer> object.</span></span>

```vb
Dim safetyTimer As New System.Windows.Forms.Timer
safetyTimer.Start()
```

<span data-ttu-id="67c20-175">Beachten Sie, dass eine Methode einfach eine *Prozedur* ist, die von einem Objekt zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="67c20-175">Note that a method is simply a *procedure* that is exposed by an object.</span></span>

<span data-ttu-id="67c20-176">Weitere Informationen finden Sie unter [Prozeduren](../procedures/index.md).</span><span class="sxs-lookup"><span data-stu-id="67c20-176">For more information, see [Procedures](../procedures/index.md).</span></span>

### <a name="events"></a><span data-ttu-id="67c20-177">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="67c20-177">Events</span></span>

<span data-ttu-id="67c20-178">Ein Ereignis ist eine Aktion, die von einem Objekt erkannt wird, etwa durch Klicken mit der Maus oder Drücken einer Taste, und für die Sie Code als Reaktion verfassen können.</span><span class="sxs-lookup"><span data-stu-id="67c20-178">An event is an action recognized by an object, such as clicking the mouse or pressing a key, and for which you can write code to respond.</span></span> <span data-ttu-id="67c20-179">Ereignisse können als Ergebnis einer Benutzeraktion oder von Programmcode auftreten bzw. vom System verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="67c20-179">Events can occur as a result of a user action or program code, or they can be caused by the system.</span></span> <span data-ttu-id="67c20-180">Code, der ein Ereignis signalisiert, soll das Ereignis *auslösen*, und Code, der darauf antwortet, soll es *abwickeln*.</span><span class="sxs-lookup"><span data-stu-id="67c20-180">Code that signals an event is said to *raise* the event, and code that responds to it is said to *handle* it.</span></span>

<span data-ttu-id="67c20-181">Sie können auch eigene, benutzerdefinierte Ereignisse entwickeln, die von Ihren Objekten ausgelöst und von anderen Objekten abgewickelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="67c20-181">You can also develop your own custom events to be raised by your objects and handled by other objects.</span></span> <span data-ttu-id="67c20-182">Weitere Informationen finden Sie unter [Ereignisse](../events/index.md).</span><span class="sxs-lookup"><span data-stu-id="67c20-182">For more information, see [Events](../events/index.md).</span></span>

### <a name="instance-members-and-shared-members"></a><span data-ttu-id="67c20-183">Instanzmember und freigegebene Member</span><span class="sxs-lookup"><span data-stu-id="67c20-183">Instance members and shared members</span></span>

<span data-ttu-id="67c20-184">Wenn Sie ein Objekt aus einer Klasse erstellen, ist das Ergebnis eine Instanz dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="67c20-184">When you create an object from a class, the result is an instance of that class.</span></span> <span data-ttu-id="67c20-185">Member, die nicht mit dem Schlüsselwort [Freigegeben](../../../language-reference/modifiers/shared.md) deklariert werden, sind *Instanzmember*, die ausschließlich zu dieser betreffenden Instanz gehören.</span><span class="sxs-lookup"><span data-stu-id="67c20-185">Members that are not declared with the [Shared](../../../language-reference/modifiers/shared.md) keyword are *instance members*, which belong strictly to that particular instance.</span></span> <span data-ttu-id="67c20-186">Ein Instanzmember in einer Instanz ist unabhängig vom gleichen Member in einer anderen Instanz derselben Klasse.</span><span class="sxs-lookup"><span data-stu-id="67c20-186">An instance member in one instance is independent of the same member in another instance of the same class.</span></span> <span data-ttu-id="67c20-187">Eine Instanzmembervariable kann beispielsweise unterschiedliche Werte in verschiedenen Instanzen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="67c20-187">An instance member variable, for example, can have different values in different instances.</span></span>

<span data-ttu-id="67c20-188">Elemente, die mit dem Schlüsselwort `Shared` deklariert werden, sind *freigegebene Member*, die zu einer Klasse als Ganzes und nicht zu einer bestimmten Instanz gehören.</span><span class="sxs-lookup"><span data-stu-id="67c20-188">Members declared with the `Shared` keyword are *shared members*, which belong to the class as a whole and not to any particular instance.</span></span> <span data-ttu-id="67c20-189">Ein freigegebener Member ist nur einmal vorhanden, unabhängig davon, wie viele Instanzen seiner Klasse Sie erstellen oder ob Sie keine Instanzen erstellen.</span><span class="sxs-lookup"><span data-stu-id="67c20-189">A shared member exists only once, no matter how many instances of its class you create, or even if you create no instances.</span></span> <span data-ttu-id="67c20-190">Eine Variable für einen freigegebenen Member enthält beispielsweise nur einen Wert, der für den gesamten Code zur Verfügung steht, der auf die Klasse zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="67c20-190">A shared member variable, for example, has only one value, which is available to all code that can access the class.</span></span>

#### <a name="accessing-non-shared-members"></a><span data-ttu-id="67c20-191">Zugreifen auf nicht freigegebene Member</span><span class="sxs-lookup"><span data-stu-id="67c20-191">Accessing non-shared members</span></span>

1. <span data-ttu-id="67c20-192">Stellen Sie sicher, dass das Objekt aus seiner Klasse erstellt und einer Objektvariablen zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="67c20-192">Make sure the object has been created from its class and assigned to an object variable.</span></span>

   ```vb
   Dim secondForm As New System.Windows.Forms.Form
   ```

2. <span data-ttu-id="67c20-193">Befolgen Sie in der Anweisung, die auf den Member zugreift, den Namen der Objektvariablen mit dem *Member-Access-Operator* ( `.` ) und dann dem Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="67c20-193">In the statement that accesses the member, follow the object variable name with the *member-access operator* (`.`) and then the member name.</span></span>

   ```vb
   secondForm.Show()
   ```

#### <a name="accessing-shared-members"></a><span data-ttu-id="67c20-194">Zugreifen auf freigegebene Member</span><span class="sxs-lookup"><span data-stu-id="67c20-194">Accessing shared members</span></span>

- <span data-ttu-id="67c20-195">Befolgen Sie den Klassennamen mit dem *Member-Access-Operator* ( `.` ) und dann dem Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="67c20-195">Follow the class name with the *member-access operator* (`.`) and then the member name.</span></span> <span data-ttu-id="67c20-196">Sie sollten einen `Shared`-Member des Objekts immer direkt über den Klassennamen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="67c20-196">You should always access a `Shared` member of the object directly through the class name.</span></span>

   ```vb
   Console.WriteLine("This computer is called " & Environment.MachineName)
   ```

- <span data-ttu-id="67c20-197">Wenn Sie bereits ein Objekt aus der Klasse erstellt haben, können Sie alternativ einen `Shared`-Member über die Variable des Objekts aufrufen.</span><span class="sxs-lookup"><span data-stu-id="67c20-197">If you have already created an object from the class, you can alternatively access a `Shared` member through the object's variable.</span></span>

### <a name="differences-between-classes-and-modules"></a><span data-ttu-id="67c20-198">Unterschiede zwischen Klassen und Modulen</span><span class="sxs-lookup"><span data-stu-id="67c20-198">Differences between classes and modules</span></span>

<span data-ttu-id="67c20-199">Der Hauptunterschied zwischen Klassen und Modulen besteht darin, dass Klassen als Objekte instanziiert werden können, während dies für Standardmodule nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="67c20-199">The main difference between classes and modules is that classes can be instantiated as objects while standard modules cannot.</span></span> <span data-ttu-id="67c20-200">Da nur eine Kopie der Daten eines Standardmoduls vorhanden ist, wenn ein Teil Ihres Programms eine öffentliche Variable in einem Standardmodul ändert, erhält jeder andere Teil des Programms denselben Wert, wenn er diese Variable anschließend liest.</span><span class="sxs-lookup"><span data-stu-id="67c20-200">Because there is only one copy of a standard module's data, when one part of your program changes a public variable in a standard module, any other part of the program gets the same value if it then reads that variable.</span></span> <span data-ttu-id="67c20-201">Im Gegensatz dazu sind Objektdaten für jedes instanziierte Objekt separat vorhanden.</span><span class="sxs-lookup"><span data-stu-id="67c20-201">In contrast, object data exists separately for each instantiated object.</span></span> <span data-ttu-id="67c20-202">Ein weiterer Unterschied ist, dass Klassen im Gegensatz zu Standardmodulen Schnittstellen implementieren können.</span><span class="sxs-lookup"><span data-stu-id="67c20-202">Another difference is that unlike standard modules, classes can implement interfaces.</span></span> <span data-ttu-id="67c20-203">Wenn eine Klasse mit dem [MustInherit](../../../language-reference/modifiers/mustinherit.md) -Modifizierer markiert ist, kann Sie nicht direkt instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="67c20-203">If a class is marked with the [MustInherit](../../../language-reference/modifiers/mustinherit.md) modifier, it can't be instantiated directly.</span></span> <span data-ttu-id="67c20-204">Es unterscheidet sich jedoch immer noch von einem Modul, da es vererbt werden kann, während Module nicht vererbt werden können.</span><span class="sxs-lookup"><span data-stu-id="67c20-204">However, it's still different from a module as it can be inherited while modules can't be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="67c20-205">Wenn der `Shared`-Modifizierer auf einen Klassenmember angewendet wird, wird er der Klasse selbst statt einer bestimmten Instanz der Klasse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="67c20-205">When the `Shared` modifier is applied to a class member, it is associated with the class itself instead of a particular instance of the class.</span></span> <span data-ttu-id="67c20-206">Der Member wird direkt mithilfe des Klassennamens aufgerufen, und zwar auf dieselbe Weise wie Modulmember.</span><span class="sxs-lookup"><span data-stu-id="67c20-206">The member is accessed directly by using the class name, the same way module members are accessed.</span></span>

<span data-ttu-id="67c20-207">Klassen und Module verwenden auch verschiedene Geltungsbereiche für ihre Mitglieder.</span><span class="sxs-lookup"><span data-stu-id="67c20-207">Classes and modules also use different scopes for their members.</span></span> <span data-ttu-id="67c20-208">Member, die innerhalb einer Klasse definiert sind, sind auf eine bestimmte Instanz der Klasse beschränkt und nur für die Lebensdauer des Objekts vorhanden.</span><span class="sxs-lookup"><span data-stu-id="67c20-208">Members defined within a class are scoped within a specific instance of the class and exist only for the lifetime of the object.</span></span> <span data-ttu-id="67c20-209">Zum Zugriff auf Member der Klasse von außerhalb einer Klasse müssen Sie vollqualifizierte Namen im Format *Objekt*.*Member* verwenden.</span><span class="sxs-lookup"><span data-stu-id="67c20-209">To access class members from outside a class, you must use fully qualified names in the format of *Object*.*Member*.</span></span>

<span data-ttu-id="67c20-210">Andererseits können die in einem Modul deklarierten Member standardmäßig öffentlich und mit jedem beliebigen Code aufgerufen werden, mit dem das Modul aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="67c20-210">On the other hand, members declared within a module are publicly accessible by default, and can be accessed by any code that can access the module.</span></span> <span data-ttu-id="67c20-211">Das bedeutet, dass Variablen in einem Standardmodul letztendlich globale Variablen sind, da sie an jeder beliebigen Stelle im Projekt sichtbar sind und für die Lebensdauer des Programms vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="67c20-211">This means that variables in a standard module are effectively global variables because they are visible from anywhere in your project, and they exist for the life of the program.</span></span>

## <a name="reusing-classes-and-objects"></a><span data-ttu-id="67c20-212">Wiederverwenden von Klassen und Objekten</span><span class="sxs-lookup"><span data-stu-id="67c20-212">Reusing classes and objects</span></span>

<span data-ttu-id="67c20-213">Mit Objekten können Sie Variablen und Prozeduren einmal deklarieren und anschließend bei Bedarf jederzeit wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="67c20-213">Objects let you declare variables and procedures once and then reuse them whenever needed.</span></span> <span data-ttu-id="67c20-214">Beispiel: Wenn Sie einer Anwendung eine Rechtschreibprüfung hinzufügen möchten, können Sie sämtliche Variablen und Supportfunktionen definieren, um die Rechtschreibprüfungsfunktion bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="67c20-214">For example, if you want to add a spelling checker to an application you could define all the variables and support functions to provide spell-checking functionality.</span></span> <span data-ttu-id="67c20-215">Wenn Sie Ihre Rechtschreibprüfung als Klasse erstellen, können Sie sie anschließend in anderen Anwendungen wiederverwenden, indem Sie einen Verweis auf die kompilierte Assembly hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="67c20-215">If you create your spelling checker as a class, you can then reuse it in other applications by adding a reference to the compiled assembly.</span></span> <span data-ttu-id="67c20-216">Sie können sich möglicherweise sogar selbst etwas Arbeit sparen, indem Sie eine Rechtschreibprüfungsklasse verwenden, die bereits von jemand anderem entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="67c20-216">Better yet, you may be able to save yourself some work by using a spelling checker class that someone else has already developed.</span></span>

<span data-ttu-id="67c20-217">.Net bietet viele Beispiele für Komponenten, die zur Verwendung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="67c20-217">.NET provides many examples of components that are available for use.</span></span> <span data-ttu-id="67c20-218">Das folgende Beispiel verwendet die <xref:System.TimeZone>-Klasse im <xref:System>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="67c20-218">The following example uses the <xref:System.TimeZone> class in the <xref:System> namespace.</span></span> <span data-ttu-id="67c20-219"><xref:System.TimeZone> enthält Member, die Ihnen das Abrufen von Informationen über die Zeitzone des aktuellen Computersystems ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="67c20-219"><xref:System.TimeZone> provides members that allow you to retrieve information about the time zone of the current computer system.</span></span>

```vb
Public Sub ExamineTimeZone()
    Dim tz As System.TimeZone = System.TimeZone.CurrentTimeZone
    Dim s As String = "Current time zone is "
    s &= CStr(tz.GetUtcOffset(Now).Hours) & " hours and "
    s &= CStr(tz.GetUtcOffset(Now).Minutes) & " minutes "
    s &= "different from UTC (coordinated universal time)"
    s &= vbCrLf & "and is currently "
    If tz.IsDaylightSavingTime(Now) = False Then s &= "not "
    s &= "on ""summer time""."
    Console.WriteLine(s)
End Sub
```

<span data-ttu-id="67c20-220">Im vorherigen Beispiel deklariert die erste [Dim-Anweisung](../../../language-reference/statements/dim-statement.md) eine Objektvariable des Typs <xref:System.TimeZone> und weist sie einem <xref:System.TimeZone>-Objekt hinzu, das von der <xref:System.TimeZone.CurrentTimeZone%2A>-Eigenschaft zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="67c20-220">In the preceding example, the first [Dim Statement](../../../language-reference/statements/dim-statement.md) declares an object variable of type <xref:System.TimeZone> and assigns to it a <xref:System.TimeZone> object returned by the <xref:System.TimeZone.CurrentTimeZone%2A> property.</span></span>

## <a name="relationships-among-objects"></a><span data-ttu-id="67c20-221">Beziehungen zwischen Objekten</span><span class="sxs-lookup"><span data-stu-id="67c20-221">Relationships among objects</span></span>

<span data-ttu-id="67c20-222">Objekte können auf verschiedene Weisen miteinander verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="67c20-222">Objects can be related to each other in several ways.</span></span> <span data-ttu-id="67c20-223">Die grundsätzlichen Arten von Beziehungen sind *Hierarchisch* und *Einschluss*.</span><span class="sxs-lookup"><span data-stu-id="67c20-223">The principal kinds of relationship are *hierarchical* and *containment*.</span></span>

### <a name="hierarchical-relationship"></a><span data-ttu-id="67c20-224">Hierarchische Beziehung</span><span class="sxs-lookup"><span data-stu-id="67c20-224">Hierarchical relationship</span></span>

<span data-ttu-id="67c20-225">Wenn Klassen von grundlegenderen Klassen abgeleitet werden, wird von einer *hierarchischen Beziehung* gesprochen.</span><span class="sxs-lookup"><span data-stu-id="67c20-225">When classes are derived from more fundamental classes, they are said to have a *hierarchical relationship*.</span></span> <span data-ttu-id="67c20-226">Klassenhierarchien sind nützlich, wenn Elemente beschrieben werden, die einen Untertyp einer allgemeineren Klasse darstellen.</span><span class="sxs-lookup"><span data-stu-id="67c20-226">Class hierarchies are useful when describing items that are a subtype of a more general class.</span></span>

<span data-ttu-id="67c20-227">Im folgenden Beispiel nehmen wir an, Sie möchten eine besondere Art eines <xref:System.Windows.Forms.Button>-Elements definieren, das wie ein normales <xref:System.Windows.Forms.Button>-Element agiert, aber auch eine Methode zur Verfügung stellt, die die Vordergrund- und Hintergrundfarben umkehrt.</span><span class="sxs-lookup"><span data-stu-id="67c20-227">In the following example, suppose you want to define a special kind of <xref:System.Windows.Forms.Button> that acts like a normal <xref:System.Windows.Forms.Button> but also exposes a method that reverses the foreground and background colors.</span></span>

#### <a name="define-a-class-that-is-derived-from-an-already-existing-class"></a><span data-ttu-id="67c20-228">Definieren einer Klasse, die von einer bereits vorhandenen Klasse abgeleitet ist</span><span class="sxs-lookup"><span data-stu-id="67c20-228">Define a class that is derived from an already existing class</span></span>

1. <span data-ttu-id="67c20-229">Verwenden Sie eine [Class-Anweisung](../../../language-reference/statements/class-statement.md) zur Definition einer Klasse, aus der das benötigte Objekt erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="67c20-229">Use a [Class Statement](../../../language-reference/statements/class-statement.md) to define a class from which to create the object you need.</span></span>

   ```vb
   Public Class ReversibleButton
   ```

   <span data-ttu-id="67c20-230">Achten Sie darauf, dass der letzten Codezeile in der Klasse eine `End Class`-Anweisung folgt.</span><span class="sxs-lookup"><span data-stu-id="67c20-230">Be sure an `End Class` statement follows the last line of code in your class.</span></span> <span data-ttu-id="67c20-231">Standardmäßig generiert die integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) bei der Eingabe einer `Class`-Anweisung automatisch ein `End Class`-Element.</span><span class="sxs-lookup"><span data-stu-id="67c20-231">By default, the integrated development environment (IDE) automatically generates an `End Class` when you enter a `Class` statement.</span></span>

2. <span data-ttu-id="67c20-232">Der `Class`-Anweisung muss sofort eine [Inherits-Anweisung](../../../language-reference/statements/inherits-statement.md) folgen.</span><span class="sxs-lookup"><span data-stu-id="67c20-232">Follow the `Class` statement immediately with an [Inherits Statement](../../../language-reference/statements/inherits-statement.md).</span></span> <span data-ttu-id="67c20-233">Geben Sie die Klasse an, von der Ihre neue Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="67c20-233">Specify the class from which your new class derives.</span></span>

   ```vb
   Inherits System.Windows.Forms.Button
   ```

   <span data-ttu-id="67c20-234">Ihre neue Klasse erbt alle Member, die von der Basisklasse definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="67c20-234">Your new class inherits all the members defined by the base class.</span></span>

3. <span data-ttu-id="67c20-235">Fügen Sie den Code für die zusätzlichen Member hinzu, die Ihre abgeleitete Klasse zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="67c20-235">Add the code for the additional members your derived class exposes.</span></span> <span data-ttu-id="67c20-236">Sie können z.B. eine `ReverseColors`-Methode hinzufügen, und die abgeleitete Klasse könnte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="67c20-236">For example, you might add a `ReverseColors` method, and your derived class might look as follows:</span></span>

   ```vb
   Public Class ReversibleButton
       Inherits System.Windows.Forms.Button
           Public Sub ReverseColors()
               Dim saveColor As System.Drawing.Color = Me.BackColor
               Me.BackColor = Me.ForeColor
               Me.ForeColor = saveColor
          End Sub
   End Class
   ```

   <span data-ttu-id="67c20-237">Wenn Sie ein Objekt aus der- `ReversibleButton` Klasse erstellen, kann es auf alle Member der <xref:System.Windows.Forms.Button> -Klasse sowie `ReverseColors` auf die-Methode und alle anderen neuen Member zugreifen, die Sie in definieren `ReversibleButton` .</span><span class="sxs-lookup"><span data-stu-id="67c20-237">If you create an object from the `ReversibleButton` class, it can access all the members of the <xref:System.Windows.Forms.Button> class, as well as the `ReverseColors` method and any other new members you define in `ReversibleButton`.</span></span>

<span data-ttu-id="67c20-238">Abgeleitete Klassen erben Member aus der Klasse, auf der sie basieren. So können Sie die Komplexität beim Vordringen in einer Klassenhierarchie steigern.</span><span class="sxs-lookup"><span data-stu-id="67c20-238">Derived classes inherit members from the class they are based on, allowing you to add complexity as you progress in a class hierarchy.</span></span> <span data-ttu-id="67c20-239">Weitere Informationen finden Sie unter [Grundlagen der Vererbung](inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="67c20-239">For more information, see [Inheritance Basics](inheritance-basics.md).</span></span>

### <a name="compile-the-code"></a><span data-ttu-id="67c20-240">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="67c20-240">Compile the code</span></span>

<span data-ttu-id="67c20-241">Achten Sie darauf, dass der Compiler die Klasse aufrufen kann, von der Ihre neue Klasse abgeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="67c20-241">Be sure the compiler can access the class from which you intend to derive your new class.</span></span> <span data-ttu-id="67c20-242">Dies kann das vollständige Qualifizieren des Namens beinhalten, wie im vorherigen Beispiel, oder das Identifizieren des Namespace in einer [Imports-Anweisung (.NET Namespace und Typ)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="67c20-242">This might mean fully qualifying its name, as in the preceding example, or identifying its namespace in an [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="67c20-243">Wenn sich die Klasse in einem anderen Projekt befindet, müssen Sie möglicherweise einen Verweis auf das Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="67c20-243">If the class is in a different project, you might need to add a reference to that project.</span></span> <span data-ttu-id="67c20-244">Weitere Informationen finden Sie unter [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project).</span><span class="sxs-lookup"><span data-stu-id="67c20-244">For more information, see [Managing references in a project](/visualstudio/ide/managing-references-in-a-project).</span></span>

### <a name="containment-relationship"></a><span data-ttu-id="67c20-245">Einschlussbeziehung</span><span class="sxs-lookup"><span data-stu-id="67c20-245">Containment relationship</span></span>

<span data-ttu-id="67c20-246">Eine andere Möglichkeit zur Verknüpfung von Objekten ist eine *Einschlussbeziehung*.</span><span class="sxs-lookup"><span data-stu-id="67c20-246">Another way that objects can be related is a *containment relationship*.</span></span> <span data-ttu-id="67c20-247">Containerobjekte schließen andere Objekte logisch ein.</span><span class="sxs-lookup"><span data-stu-id="67c20-247">Container objects logically encapsulate other objects.</span></span> <span data-ttu-id="67c20-248">Beispielsweise enthält das <xref:System.OperatingSystem>-Objekt ein <xref:System.Version>-Objekt logisch, das es durch seine <xref:System.OperatingSystem.Version%2A>-Eigenschaft zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="67c20-248">For example, the <xref:System.OperatingSystem> object logically contains a <xref:System.Version> object, which it returns through its <xref:System.OperatingSystem.Version%2A> property.</span></span> <span data-ttu-id="67c20-249">Beachten Sie, dass das Container-Objekt physisch kein anderes Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="67c20-249">Note that the container object does not physically contain any other object.</span></span>

#### <a name="collections"></a><span data-ttu-id="67c20-250">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="67c20-250">Collections</span></span>

<span data-ttu-id="67c20-251">Ein bestimmter Typ des Objekteinschlusses wird dargestellt durch *Auflistungen*.</span><span class="sxs-lookup"><span data-stu-id="67c20-251">One particular type of object containment is represented by *collections*.</span></span> <span data-ttu-id="67c20-252">Auflistungen sind Gruppen ähnlicher Objekte, die aufgelistet werden können.</span><span class="sxs-lookup"><span data-stu-id="67c20-252">Collections are groups of similar objects that can be enumerated.</span></span> <span data-ttu-id="67c20-253">Visual Basic unterstützt eine bestimmte Syntax in der [for each... Die nächste Anweisung](../../../language-reference/statements/for-each-next-statement.md) , die das Durchlaufen der Elemente einer Auflistung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="67c20-253">Visual Basic supports a specific syntax in the [For Each...Next Statement](../../../language-reference/statements/for-each-next-statement.md) that allows you to iterate through the items of a collection.</span></span> <span data-ttu-id="67c20-254">Zudem ermöglichen Auflistungen die Verwendung eines <xref:Microsoft.VisualBasic.Collection.Item%2A>-Elements zum Abrufen von Elementen anhand ihres Indexes oder anhand der Zuordnung zu einer eindeutigen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="67c20-254">Additionally, collections often allow you to use an <xref:Microsoft.VisualBasic.Collection.Item%2A> to retrieve elements by their index or by associating them with a unique string.</span></span> <span data-ttu-id="67c20-255">Auflistungen können einfacher verwendet werden als Arrays, denn Sie können sie zum Hinzufügen oder Entfernen von Elementen ohne Indizes verwenden.</span><span class="sxs-lookup"><span data-stu-id="67c20-255">Collections can be easier to use than arrays because they allow you to add or remove items without using indexes.</span></span> <span data-ttu-id="67c20-256">Aufgrund ihrer Benutzerfreundlichkeit werden Auflistungen häufig zum Speichern von Formularen und Steuerelementen verwendet.</span><span class="sxs-lookup"><span data-stu-id="67c20-256">Because of their ease of use, collections are often used to store forms and controls.</span></span>

## <a name="related-topics"></a><span data-ttu-id="67c20-257">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="67c20-257">Related topics</span></span>

<span data-ttu-id="67c20-258">[Exemplarische Vorgehensweise: Definieren von Klassen](walkthrough-defining-classes.md)</span><span class="sxs-lookup"><span data-stu-id="67c20-258">[Walkthrough: Defining Classes](walkthrough-defining-classes.md)</span></span>\
<span data-ttu-id="67c20-259">Stellt eine schrittweise Beschreibung des Erstellens einer Klasse bereit.</span><span class="sxs-lookup"><span data-stu-id="67c20-259">Provides a step-by-step description of how to create a class.</span></span>

<span data-ttu-id="67c20-260">[Überladene Eigenschaften und Methoden](overloaded-properties-and-methods.md)</span><span class="sxs-lookup"><span data-stu-id="67c20-260">[Overloaded Properties and Methods](overloaded-properties-and-methods.md)</span></span>\
<span data-ttu-id="67c20-261">Überladene Eigenschaften und Methoden</span><span class="sxs-lookup"><span data-stu-id="67c20-261">Overloaded Properties and Methods</span></span>

<span data-ttu-id="67c20-262">[Vererbungs Grundlagen](inheritance-basics.md)</span><span class="sxs-lookup"><span data-stu-id="67c20-262">[Inheritance Basics](inheritance-basics.md)</span></span>\
<span data-ttu-id="67c20-263">Beschreibt die Vererbungsmodifizierer, das Außerkraftsetzen von Methoden und Eigenschaften, MyClass und MyBase.</span><span class="sxs-lookup"><span data-stu-id="67c20-263">Covers inheritance modifiers, overriding methods and properties, MyClass, and MyBase.</span></span>

<span data-ttu-id="67c20-264">[Objekt Lebensdauer: Erstellen und zerstören von Objekten](object-lifetime-how-objects-are-created-and-destroyed.md)</span><span class="sxs-lookup"><span data-stu-id="67c20-264">[Object Lifetime: How Objects Are Created and Destroyed](object-lifetime-how-objects-are-created-and-destroyed.md)</span></span>\
<span data-ttu-id="67c20-265">Erläutert das Erstellen und Entfernen von Klasseninstanzen.</span><span class="sxs-lookup"><span data-stu-id="67c20-265">Discusses creating and disposing of class instances.</span></span>

<span data-ttu-id="67c20-266">[Anonyme Typen](anonymous-types.md)</span><span class="sxs-lookup"><span data-stu-id="67c20-266">[Anonymous Types](anonymous-types.md)</span></span>\
<span data-ttu-id="67c20-267">Beschreibt das Erstellen und Verwenden von anonymen Typen, die Ihnen das Erstellen von Objekten ermöglichen, ohne eine Klassendefinition für den Datentyp zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="67c20-267">Describes how to create and use anonymous types, which allow you to create objects without writing a class definition for the data type.</span></span>

<span data-ttu-id="67c20-268">[Objektinitialisierer: benannte und anonyme Typen](object-initializers-named-and-anonymous-types.md)</span><span class="sxs-lookup"><span data-stu-id="67c20-268">[Object Initializers: Named and Anonymous Types](object-initializers-named-and-anonymous-types.md)</span></span>\
<span data-ttu-id="67c20-269">Erläutert Objektinitialisierer, die zum Erstellen von Instanzen von benannten und anonymen Typen mit einem einzelnen Ausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="67c20-269">Discusses object initializers, which are used to create instances of named and anonymous types by using a single expression.</span></span>

<span data-ttu-id="67c20-270">[Gewusst wie: Ableiten von Eigenschaften Namen und Typen in Deklarationen anonymer Typen](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)</span><span class="sxs-lookup"><span data-stu-id="67c20-270">[How to: Infer Property Names and Types in Anonymous Type Declarations](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)</span></span>\
<span data-ttu-id="67c20-271">Erklärt das Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen.</span><span class="sxs-lookup"><span data-stu-id="67c20-271">Explains how to infer property names and types in anonymous type declarations.</span></span> <span data-ttu-id="67c20-272">Stellt Beispiele für erfolgreiche und fehlgeschlagene Ableitungen bereit.</span><span class="sxs-lookup"><span data-stu-id="67c20-272">Provides examples of successful and unsuccessful inference.</span></span>
