---
title: 'Gewusst wie: Zugreifen auf Member eines Objekts'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: d44b538e8413eb1412e937375e9bca77600a29b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348670"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a><span data-ttu-id="85000-102">Gewusst wie: Zugreifen auf Member eines Objekts (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85000-102">How to: Access Members of an Object (Visual Basic)</span></span>

<span data-ttu-id="85000-103">Wenn Sie über eine Objekt Variable verfügen, die auf ein Objekt verweist, sollten Sie häufig mit den Membern dieses Objekts arbeiten, z. b. die Methoden, Eigenschaften, Felder und Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="85000-103">When you have an object variable that refers to an object, you often want to work with the members of that object, such as its methods, properties, fields, and events.</span></span> <span data-ttu-id="85000-104">Wenn Sie z. b. ein neues <xref:System.Windows.Forms.Form> Objekt erstellt haben, möchten Sie möglicherweise seine <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft festlegen oder seine <xref:System.Windows.Forms.Control.Focus%2A>-Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="85000-104">For example, once you have created a new <xref:System.Windows.Forms.Form> object, you might want to set its <xref:System.Windows.Forms.Control.Text%2A> property or call its <xref:System.Windows.Forms.Control.Focus%2A> method.</span></span>

## <a name="accessing-members"></a><span data-ttu-id="85000-105">Zugreifen auf Member</span><span class="sxs-lookup"><span data-stu-id="85000-105">Accessing Members</span></span>

<span data-ttu-id="85000-106">Sie greifen auf die Member eines Objekts über die Variable zu, die darauf verweist.</span><span class="sxs-lookup"><span data-stu-id="85000-106">You access an object's members through the variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object"></a><span data-ttu-id="85000-107">So greifen Sie auf Member eines Objekts zu</span><span class="sxs-lookup"><span data-stu-id="85000-107">To access members of an object</span></span>

- <span data-ttu-id="85000-108">Verwenden Sie den Member-Access-Operator (`.`) zwischen dem Objektvariablen Namen und dem Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="85000-108">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    currentText = newForm.Text
    ```

    <span data-ttu-id="85000-109">Wenn der Member frei [gegeben](../../../../visual-basic/language-reference/modifiers/shared.md)ist, benötigen Sie keine Variable, um darauf zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="85000-109">If the member is [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), you do not need a variable to access it.</span></span>

## <a name="accessing-members-of-an-object-of-known-type"></a><span data-ttu-id="85000-110">Zugreifen auf Member eines Objekts des bekannten Typs</span><span class="sxs-lookup"><span data-stu-id="85000-110">Accessing Members of an Object of Known Type</span></span>

<span data-ttu-id="85000-111">Wenn Sie den Typ eines Objekts zur Kompilierzeit kennen, können Sie eine *frühe Bindung* für eine Variable verwenden, die darauf verweist.</span><span class="sxs-lookup"><span data-stu-id="85000-111">If you know the type of an object at compile time, you can use *early binding* for a variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a><span data-ttu-id="85000-112">So greifen Sie auf Member eines Objekts zu, für das Sie den Typ zur Kompilierzeit kennen</span><span class="sxs-lookup"><span data-stu-id="85000-112">To access members of an object for which you know the type at compile time</span></span>

1. <span data-ttu-id="85000-113">Deklarieren Sie die Objekt Variable als Typ des Objekts, das Sie der Variablen zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="85000-113">Declare the object variable to be of the type of the object you intend to assign to the variable.</span></span>

    ```vb
    Dim extraForm As System.Windows.Forms.Form
    ```

    <span data-ttu-id="85000-114">Mit `Option Strict On`können Sie nur <xref:System.Windows.Forms.Form> Objekte (oder Objekte eines Typs, die von <xref:System.Windows.Forms.Form>abgeleitet sind) `extraForm`zuweisen.</span><span class="sxs-lookup"><span data-stu-id="85000-114">With `Option Strict On`, you can assign only <xref:System.Windows.Forms.Form> objects (or objects of a type derived from <xref:System.Windows.Forms.Form>) to `extraForm`.</span></span> <span data-ttu-id="85000-115">Wenn Sie eine Klasse oder Struktur mit erweiternde `CType` Konvertierung in <xref:System.Windows.Forms.Form>definiert haben, können Sie diese Klasse oder Struktur auch `extraForm`zuweisen.</span><span class="sxs-lookup"><span data-stu-id="85000-115">If you have defined a class or structure with a widening `CType` conversion to <xref:System.Windows.Forms.Form>, you can also assign that class or structure to `extraForm`.</span></span>

2. <span data-ttu-id="85000-116">Verwenden Sie den Member-Access-Operator (`.`) zwischen dem Objektvariablen Namen und dem Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="85000-116">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    extraForm.Show()
    ```

    <span data-ttu-id="85000-117">Sie können auf alle Methoden und Eigenschaften zugreifen, die für die <xref:System.Windows.Forms.Form>-Klasse spezifisch sind, unabhängig von der `Option Strict` Einstellung.</span><span class="sxs-lookup"><span data-stu-id="85000-117">You can access all of the methods and properties specific to the <xref:System.Windows.Forms.Form> class, no matter what the `Option Strict` setting is.</span></span>

## <a name="accessing-members-of-an-object-of-unknown-type"></a><span data-ttu-id="85000-118">Zugreifen auf Member eines Objekts mit einem unbekannten Typ</span><span class="sxs-lookup"><span data-stu-id="85000-118">Accessing Members of an Object of Unknown Type</span></span>

<span data-ttu-id="85000-119">Wenn Sie den Typ eines Objekts zur Kompilierzeit nicht kennen, müssen Sie für jede Variable, die darauf verweist, die *späte Bindung* verwenden.</span><span class="sxs-lookup"><span data-stu-id="85000-119">If you do not know the type of an object at compile time, you must use *late binding* for any variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a><span data-ttu-id="85000-120">So greifen Sie auf Member eines Objekts zu, für das der Typ zur Kompilierzeit nicht bekannt ist</span><span class="sxs-lookup"><span data-stu-id="85000-120">To access members of an object for which you do not know the type at compile time</span></span>

1. <span data-ttu-id="85000-121">Deklarieren Sie die Objekt Variable als [Objekt Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="85000-121">Declare the object variable to be of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="85000-122">(Das Deklarieren einer Variablen als `Object` entspricht der Deklaration als <xref:System.Object?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="85000-122">(Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.)</span></span>

    ```vb
    Dim someControl As Object
    ```

    <span data-ttu-id="85000-123">Mit `Option Strict On`können Sie nur auf die Member zugreifen, die für die <xref:System.Object> Klasse definiert sind.</span><span class="sxs-lookup"><span data-stu-id="85000-123">With `Option Strict On`, you can access only the members that are defined on the <xref:System.Object> class.</span></span>

2. <span data-ttu-id="85000-124">Verwenden Sie den Member-Access-Operator (`.`) zwischen dem Objektvariablen Namen und dem Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="85000-124">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    someControl.GetType()
    ```

    <span data-ttu-id="85000-125">Um auf die Member eines beliebigen Objekts zugreifen zu können, das Sie der Objektvariablen zuweisen, müssen Sie `Option Strict Off`festlegen.</span><span class="sxs-lookup"><span data-stu-id="85000-125">To be able to access the members of any object you assign to the object variable, you must set `Option Strict Off`.</span></span> <span data-ttu-id="85000-126">Wenn Sie dies tun, kann der Compiler nicht garantieren, dass ein angegebenes Element von dem Objekt verfügbar gemacht wird, das Sie der Variablen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="85000-126">When you do this, the compiler cannot guarantee that a given member is exposed by the object you assign to the variable.</span></span> <span data-ttu-id="85000-127">Wenn das Objekt keinen Member verfügbar macht, auf den Sie zugreifen möchten, tritt eine <xref:System.MemberAccessException> Ausnahme auf.</span><span class="sxs-lookup"><span data-stu-id="85000-127">If the object does not expose a member you attempt to access, a <xref:System.MemberAccessException> exception occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="85000-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85000-128">See also</span></span>

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [<span data-ttu-id="85000-129">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="85000-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="85000-130">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="85000-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="85000-131">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="85000-131">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="85000-132">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="85000-132">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
