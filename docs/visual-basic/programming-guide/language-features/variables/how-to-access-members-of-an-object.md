---
title: 'Vorgehensweise: Zugreifen auf Member eines Objekts (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: de00e428cc3d9d7a5688e853b0ff4295fec5b3e9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322757"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a><span data-ttu-id="de0a1-102">Vorgehensweise: Zugreifen auf Member eines Objekts (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de0a1-102">How to: Access Members of an Object (Visual Basic)</span></span>
<span data-ttu-id="de0a1-103">Wenn Sie eine Objektvariablen, die auf ein Objekt verweist verfügen, möchten Sie häufig die Member des Objekts, z. B. die Methoden, Eigenschaften, Felder und Ereignisse zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="de0a1-103">When you have an object variable that refers to an object, you often want to work with the members of that object, such as its methods, properties, fields, and events.</span></span> <span data-ttu-id="de0a1-104">Angenommen, nachdem Sie erstellt haben ein neues <xref:System.Windows.Forms.Form> -Objekts können Sie festlegen möchten die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft oder der Aufruf der <xref:System.Windows.Forms.Control.Focus%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="de0a1-104">For example, once you have created a new <xref:System.Windows.Forms.Form> object, you might want to set its <xref:System.Windows.Forms.Control.Text%2A> property or call its <xref:System.Windows.Forms.Control.Focus%2A> method.</span></span>  
  
## <a name="accessing-members"></a><span data-ttu-id="de0a1-105">Zugreifen auf Member</span><span class="sxs-lookup"><span data-stu-id="de0a1-105">Accessing Members</span></span>  
 <span data-ttu-id="de0a1-106">Sie können die Mitglieder eines Objekts zugreifen, über die Variable, die darauf verweist.</span><span class="sxs-lookup"><span data-stu-id="de0a1-106">You access an object's members through the variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object"></a><span data-ttu-id="de0a1-107">Auf Member eines Objekts zugreifen.</span><span class="sxs-lookup"><span data-stu-id="de0a1-107">To access members of an object</span></span>  
  
-   <span data-ttu-id="de0a1-108">Verwenden Sie den Memberzugriffsoperator (`.`) zwischen den Namen der Objektvariablen und den Namen des Members.</span><span class="sxs-lookup"><span data-stu-id="de0a1-108">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     <span data-ttu-id="de0a1-109">Wenn der Member ist [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), eine Variable für den Zugriff ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="de0a1-109">If the member is [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), you do not need a variable to access it.</span></span>  
  
## <a name="accessing-members-of-an-object-of-known-type"></a><span data-ttu-id="de0a1-110">Zugreifen auf Member eines Objekts vom bekannten Typ</span><span class="sxs-lookup"><span data-stu-id="de0a1-110">Accessing Members of an Object of Known Type</span></span>  
 <span data-ttu-id="de0a1-111">Wenn Sie den Typ eines Objekts zur Kompilierungszeit kennen, können Sie *frühe Bindung* für eine Variable, die darauf verweist.</span><span class="sxs-lookup"><span data-stu-id="de0a1-111">If you know the type of an object at compile time, you can use *early binding* for a variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a><span data-ttu-id="de0a1-112">Auf Member eines Objekts, für die der Typ zur Kompilierzeit unbekannt</span><span class="sxs-lookup"><span data-stu-id="de0a1-112">To access members of an object for which you know the type at compile time</span></span>  
  
1. <span data-ttu-id="de0a1-113">Deklarieren Sie die Objektvariable vom Typ des Objekts sein, die Sie der Variable zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="de0a1-113">Declare the object variable to be of the type of the object you intend to assign to the variable.</span></span>  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     <span data-ttu-id="de0a1-114">Mit `Option Strict On`, Sie können nur zuweisen <xref:System.Windows.Forms.Form> Objekte (oder davon abgeleitete Objekte eines Typs <xref:System.Windows.Forms.Form>) zu `extraForm`.</span><span class="sxs-lookup"><span data-stu-id="de0a1-114">With `Option Strict On`, you can assign only <xref:System.Windows.Forms.Form> objects (or objects of a type derived from <xref:System.Windows.Forms.Form>) to `extraForm`.</span></span> <span data-ttu-id="de0a1-115">Wenn Sie eine Klasse oder Struktur mit einer erweiternden definiert haben `CType` Konvertierung in <xref:System.Windows.Forms.Form>, Sie können auch weisen Sie dieser Klasse oder-Struktur in `extraForm`.</span><span class="sxs-lookup"><span data-stu-id="de0a1-115">If you have defined a class or structure with a widening `CType` conversion to <xref:System.Windows.Forms.Form>, you can also assign that class or structure to `extraForm`.</span></span>  
  
2. <span data-ttu-id="de0a1-116">Verwenden Sie den Memberzugriffsoperator (`.`) zwischen den Namen der Objektvariablen und den Namen des Members.</span><span class="sxs-lookup"><span data-stu-id="de0a1-116">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    extraForm.Show()  
    ```  
  
     <span data-ttu-id="de0a1-117">Sie können Zugriff auf alle Methoden und Eigenschaften, die spezifisch für die <xref:System.Windows.Forms.Form> -Klasse, unabhängig davon, was die `Option Strict` Einstellung ist.</span><span class="sxs-lookup"><span data-stu-id="de0a1-117">You can access all of the methods and properties specific to the <xref:System.Windows.Forms.Form> class, no matter what the `Option Strict` setting is.</span></span>  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a><span data-ttu-id="de0a1-118">Zugreifen auf Member eines Objekts eines unbekannten Typs</span><span class="sxs-lookup"><span data-stu-id="de0a1-118">Accessing Members of an Object of Unknown Type</span></span>  
 <span data-ttu-id="de0a1-119">Wenn Sie den Typ eines Objekts zur Kompilierzeit nicht kennen, können Sie mit *späte Bindung* für jede Variable, die darauf verweist.</span><span class="sxs-lookup"><span data-stu-id="de0a1-119">If you do not know the type of an object at compile time, you must use *late binding* for any variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a><span data-ttu-id="de0a1-120">Auf Member eines Objekts, für die Sie nicht den Typ zur Kompilierzeit kennen</span><span class="sxs-lookup"><span data-stu-id="de0a1-120">To access members of an object for which you do not know the type at compile time</span></span>  
  
1. <span data-ttu-id="de0a1-121">Deklarieren Sie die Objektvariable, der die [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="de0a1-121">Declare the object variable to be of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="de0a1-122">(Deklaration einer Variablen als `Object` ist identisch mit der Deklaration als <xref:System.Object?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="de0a1-122">(Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.)</span></span>  
  
    ```  
    Dim someControl As Object  
    ```  
  
     <span data-ttu-id="de0a1-123">Mit `Option Strict On`, es stehen nur die Elemente, die auf definierten die <xref:System.Object> Klasse.</span><span class="sxs-lookup"><span data-stu-id="de0a1-123">With `Option Strict On`, you can access only the members that are defined on the <xref:System.Object> class.</span></span>  
  
2. <span data-ttu-id="de0a1-124">Verwenden Sie den Memberzugriffsoperator (`.`) zwischen den Namen der Objektvariablen und den Namen des Members.</span><span class="sxs-lookup"><span data-stu-id="de0a1-124">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    someControl.GetType()  
    ```  
  
     <span data-ttu-id="de0a1-125">Um den Zugriff auf Member eines Objekts Sie die Objektvariable zuweisen, müssen Sie festlegen, `Option Strict Off`.</span><span class="sxs-lookup"><span data-stu-id="de0a1-125">To be able to access the members of any object you assign to the object variable, you must set `Option Strict Off`.</span></span> <span data-ttu-id="de0a1-126">Wenn Sie dies tun, kann nicht der Compiler nicht garantieren, dass ein bestimmtes Element durch das Objekt verfügbar gemacht wird, die Sie der Variablen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="de0a1-126">When you do this, the compiler cannot guarantee that a given member is exposed by the object you assign to the variable.</span></span> <span data-ttu-id="de0a1-127">Wenn das Objekt keinen Member verfügbar macht, Sie versuchen, die für den Zugriff auf, eine <xref:System.MemberAccessException> Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="de0a1-127">If the object does not expose a member you attempt to access, a <xref:System.MemberAccessException> exception occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de0a1-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de0a1-128">See also</span></span>

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [<span data-ttu-id="de0a1-129">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="de0a1-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="de0a1-130">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="de0a1-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="de0a1-131">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="de0a1-131">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="de0a1-132">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="de0a1-132">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
