---
title: 'Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], creating property grids for user settings
- user settings [Visual Basic], creating property grids
- property grids [Visual Basic], creating for user settings
- property grids
ms.assetid: b0bc737e-50d1-43d1-a6df-268db6e6f91c
ms.openlocfilehash: bed4e8a2b50f0115c3b8d9d6abf427df5f216388
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74329612"
---
# <a name="how-to-create-property-grids-for-user-settings-in-visual-basic"></a><span data-ttu-id="143eb-102">Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="143eb-102">How to: Create Property Grids for User Settings in Visual Basic</span></span>

<span data-ttu-id="143eb-103">Sie können ein Eigenschaftenraster für Benutzereinstellungen erstellen, indem Sie ein <xref:System.Windows.Forms.PropertyGrid>-Steuerelement mit den Benutzereinstellungseigenschaften des `My.Settings`-Objekts auffüllen.</span><span class="sxs-lookup"><span data-stu-id="143eb-103">You can create a property grid for user settings by populating a <xref:System.Windows.Forms.PropertyGrid> control with the user setting properties of the `My.Settings` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="143eb-104">Damit dieses Beispiel funktioniert, muss Ihre Anwendung über konfigurierte Benutzereinstellungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="143eb-104">In order for this example to work, your application must have its user settings configured.</span></span> <span data-ttu-id="143eb-105">Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="143eb-105">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
 <span data-ttu-id="143eb-106">Das `My.Settings`-Objekt macht jede Einstellung als Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="143eb-106">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="143eb-107">Der Eigenschaftenname ist identisch mit dem Einstellungsnamen, und der Eigenschaftentyp entspricht dem Typ der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="143eb-107">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="143eb-108">Der **Bereich** der Einstellung gibt an, ob die Eigenschaft schreibgeschützt ist; die Eigenschaft für den Bereich **Anwendung** ist schreibgeschützt, während die Eigenschaft für die Bereichseinstellung **Benutzer** über einen Lese-/Schreibzugriff verfügt.</span><span class="sxs-lookup"><span data-stu-id="143eb-108">The setting's **Scope** determines if the property is read-only; the property for an **Application**-scope setting is read-only, while the property for a **User**-scope setting is read-write.</span></span> <span data-ttu-id="143eb-109">Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="143eb-109">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="143eb-110">Sie können die Werte der Einstellungen für den Anwendungsbereich zur Laufzeit nicht ändern oder speichern.</span><span class="sxs-lookup"><span data-stu-id="143eb-110">You cannot change or save the values of application-scope settings at run time.</span></span> <span data-ttu-id="143eb-111">Einstellungen für den Anwendungsbereich können nur geändert werden, wenn Sie die Anwendung (über den **Projekt-Designer**) erstellen, oder indem Sie die Anwendungskonfigurationsdatei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="143eb-111">Application-scope settings can be changed only when creating the application (through the **Project Designer**) or by editing the application's configuration file.</span></span> <span data-ttu-id="143eb-112">Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="143eb-112">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
 <span data-ttu-id="143eb-113">Dieses Beispiel verwendet ein <xref:System.Windows.Forms.PropertyGrid>-Steuerelement, um auf die Benutzereinstellungseigenschaften des `My.Settings`-Objekts zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="143eb-113">This example uses a <xref:System.Windows.Forms.PropertyGrid> control to access the user-setting properties of the `My.Settings` object.</span></span> <span data-ttu-id="143eb-114">In der Standardeinstellung zeigt <xref:System.Windows.Forms.PropertyGrid> alle Eigenschaften des `My.Settings`-Objekts an.</span><span class="sxs-lookup"><span data-stu-id="143eb-114">By default, the <xref:System.Windows.Forms.PropertyGrid> shows all the properties of the `My.Settings` object.</span></span> <span data-ttu-id="143eb-115">Die Eigenschaften von Benutzereinstellungen müssen jedoch das <xref:System.Configuration.UserScopedSettingAttribute>-Attribut aufweisen.</span><span class="sxs-lookup"><span data-stu-id="143eb-115">However, the user-setting properties have the <xref:System.Configuration.UserScopedSettingAttribute> attribute.</span></span> <span data-ttu-id="143eb-116">In diesem Beispiel wird die <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A>-Eigenschaft von <xref:System.Windows.Forms.PropertyGrid> auf <xref:System.Configuration.UserScopedSettingAttribute> festgelegt, um nur die Eigenschaften von Benutzereinstellungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="143eb-116">This example sets the <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> property of the <xref:System.Windows.Forms.PropertyGrid> to <xref:System.Configuration.UserScopedSettingAttribute> to display only the user-setting properties.</span></span>  
  
### <a name="to-add-a-user-setting-property-grid"></a><span data-ttu-id="143eb-117">So fügen Sie ein Eigenschaftenraster für Benutzereinstellungen hinzu</span><span class="sxs-lookup"><span data-stu-id="143eb-117">To add a user setting property grid</span></span>  
  
1. <span data-ttu-id="143eb-118">Fügen Sie das **PropertyGrid**-Steuerelement aus der **Toolbox** der Entwurfsoberfläche für Ihre Anwendung hinzu, von der davon ausgegangen wird, dass sie `Form1` ist.</span><span class="sxs-lookup"><span data-stu-id="143eb-118">Add the **PropertyGrid** control from the **Toolbox** to the design surface for your application, assumed here to be `Form1`.</span></span>  
  
     <span data-ttu-id="143eb-119">Der Standardname für das Steuerelement des Eigenschaftenrasters ist `PropertyGrid1`.</span><span class="sxs-lookup"><span data-stu-id="143eb-119">The default name of the property-grid control is `PropertyGrid1`.</span></span>  
  
2. <span data-ttu-id="143eb-120">Doppelklicken Sie auf die Entwurfsoberfläche für `Form1`, um den Code für den Ereignishandler zum Laden von Formularen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="143eb-120">Double-click the design surface for `Form1` to open the code for the form-load event handler.</span></span>  
  
3. <span data-ttu-id="143eb-121">Legen Sie das `My.Settings`-Objekt als ausgewähltes Objekt für das Eigenschaftenraster fest.</span><span class="sxs-lookup"><span data-stu-id="143eb-121">Set the `My.Settings` object as the selected object for the property grid.</span></span>  
  
     [!code-vb[VbVbalrMyResources#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#11)]  
  
4. <span data-ttu-id="143eb-122">Konfigurieren Sie das Eigenschaftenraster so, dass nur die Benutzereinstellungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="143eb-122">Configure the property grid to show only the user settings.</span></span>  
  
     [!code-vb[VbVbalrMyResources#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#12)]  
  
    > [!NOTE]
    > <span data-ttu-id="143eb-123">Um nur die Einstellungen des Anwendungsbereichs anzuzeigen, verwenden Sie das <xref:System.Configuration.ApplicationScopedSettingAttribute>-Attribut anstelle von <xref:System.Configuration.UserScopedSettingAttribute>.</span><span class="sxs-lookup"><span data-stu-id="143eb-123">To show only the application-scope settings, use the <xref:System.Configuration.ApplicationScopedSettingAttribute> attribute instead of  <xref:System.Configuration.UserScopedSettingAttribute>.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="143eb-124">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="143eb-124">Robust Programming</span></span>  

 <span data-ttu-id="143eb-125">Die Anwendung speichert die Benutzereinstellungen beim Herunterfahren der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="143eb-125">The application saves the user settings when the application shuts down.</span></span> <span data-ttu-id="143eb-126">Um die Einstellungen sofort zu speichern, rufen Sie die `My.Settings.Save`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="143eb-126">To save the settings immediately, call the `My.Settings.Save` method.</span></span> <span data-ttu-id="143eb-127">Weitere Informationen finden Sie unter [Vorgehensweise: Beibehalten von Benutzereinstellungen](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span><span class="sxs-lookup"><span data-stu-id="143eb-127">For more information, see [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="143eb-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="143eb-128">See also</span></span>

- [<span data-ttu-id="143eb-129">My.Settings-Objekt</span><span class="sxs-lookup"><span data-stu-id="143eb-129">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="143eb-130">How to: Lesen von Anwendungseinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="143eb-130">How to: Read Application Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="143eb-131">How to: Ändern von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="143eb-131">How to: Change User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="143eb-132">How to: Beibehalten von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="143eb-132">How to: Persist User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="143eb-133">Verwalten von Anwendungseinstellungen (.NET)</span><span class="sxs-lookup"><span data-stu-id="143eb-133">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
