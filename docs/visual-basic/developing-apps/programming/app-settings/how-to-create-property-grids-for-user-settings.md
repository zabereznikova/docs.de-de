---
title: "Gewusst wie: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Settings object, creating property grids for user settings
- user settings, creating property grids
- property grids, creating for user settings
- property grids
ms.assetid: b0bc737e-50d1-43d1-a6df-268db6e6f91c
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c21b458f9c28f4d25e5b0d8099b9a5255f31ac52
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-property-grids-for-user-settings-in-visual-basic"></a><span data-ttu-id="2fd32-102">Gewusst wie: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2fd32-102">How to: Create Property Grids for User Settings in Visual Basic</span></span>
<span data-ttu-id="2fd32-103">Sie können ein Eigenschaftenraster für Benutzereinstellungen erstellen, indem Sie ein <xref:System.Windows.Forms.PropertyGrid>-Steuerelement mit den Benutzereinstellungseigenschaften des `My.Settings`-Objekts auffüllen.</span><span class="sxs-lookup"><span data-stu-id="2fd32-103">You can create a property grid for user settings by populating a <xref:System.Windows.Forms.PropertyGrid> control with the user setting properties of the `My.Settings` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2fd32-104">Damit dieses Beispiel funktioniert, muss Ihre Anwendung über konfigurierte Benutzereinstellungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="2fd32-104">In order for this example to work, your application must have its user settings configured.</span></span> <span data-ttu-id="2fd32-105">Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="2fd32-105">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
 <span data-ttu-id="2fd32-106">Das `My.Settings`-Objekt macht jede Einstellung als Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2fd32-106">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="2fd32-107">Der Eigenschaftenname ist identisch mit dem Einstellungsnamen, und der Eigenschaftentyp entspricht dem Typ der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="2fd32-107">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="2fd32-108">Der **Bereich** der Einstellung gibt an, ob die Eigenschaft schreibgeschützt ist; die Eigenschaft für den Bereich **Anwendung** ist schreibgeschützt, während die Eigenschaft für die Bereichseinstellung **Benutzer** über einen Lese-/Schreibzugriff verfügt.</span><span class="sxs-lookup"><span data-stu-id="2fd32-108">The setting's **Scope** determines if the property is read-only; the property for an **Application**-scope setting is read-only, while the property for a **User**-scope setting is read-write.</span></span> <span data-ttu-id="2fd32-109">Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="2fd32-109">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2fd32-110">Sie können die Werte der Einstellungen für den Anwendungsbereich zur Laufzeit nicht ändern oder speichern.</span><span class="sxs-lookup"><span data-stu-id="2fd32-110">You cannot change or save the values of application-scope settings at run time.</span></span> <span data-ttu-id="2fd32-111">Einstellungen für den Anwendungsbereich können nur geändert werden, wenn Sie die Anwendung (über den **Projekt-Designer**) erstellen, oder indem Sie die Anwendungskonfigurationsdatei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2fd32-111">Application-scope settings can be changed only when creating the application (through the **Project Designer**) or by editing the application's configuration file.</span></span> <span data-ttu-id="2fd32-112">Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="2fd32-112">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
 <span data-ttu-id="2fd32-113">Dieses Beispiel verwendet ein <xref:System.Windows.Forms.PropertyGrid>-Steuerelement, um auf die Benutzereinstellungseigenschaften des `My.Settings`-Objekts zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="2fd32-113">This example uses a <xref:System.Windows.Forms.PropertyGrid> control to access the user-setting properties of the `My.Settings` object.</span></span> <span data-ttu-id="2fd32-114">In der Standardeinstellung zeigt <xref:System.Windows.Forms.PropertyGrid> alle Eigenschaften des `My.Settings`-Objekts an.</span><span class="sxs-lookup"><span data-stu-id="2fd32-114">By default, the <xref:System.Windows.Forms.PropertyGrid> shows all the properties of the `My.Settings` object.</span></span> <span data-ttu-id="2fd32-115">Die Eigenschaften von Benutzereinstellungen müssen jedoch das <xref:System.Configuration.UserScopedSettingAttribute>-Attribut aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2fd32-115">However, the user-setting properties have the <xref:System.Configuration.UserScopedSettingAttribute> attribute.</span></span> <span data-ttu-id="2fd32-116">In diesem Beispiel wird die <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A>-Eigenschaft von <xref:System.Windows.Forms.PropertyGrid> auf <xref:System.Configuration.UserScopedSettingAttribute> festgelegt, um nur die Eigenschaften von Benutzereinstellungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2fd32-116">This example sets the <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> property of the <xref:System.Windows.Forms.PropertyGrid> to <xref:System.Configuration.UserScopedSettingAttribute> to display only the user-setting properties.</span></span>  
  
### <a name="to-add-a-user-setting-property-grid"></a><span data-ttu-id="2fd32-117">So fügen Sie ein Eigenschaftenraster für Benutzereinstellungen hinzu</span><span class="sxs-lookup"><span data-stu-id="2fd32-117">To add a user setting property grid</span></span>  
  
1.  <span data-ttu-id="2fd32-118">Fügen Sie das **PropertyGrid**-Steuerelement aus der **Toolbox** der Entwurfsoberfläche für Ihre Anwendung hinzu, von der davon ausgegangen wird, dass sie `Form1` ist.</span><span class="sxs-lookup"><span data-stu-id="2fd32-118">Add the **PropertyGrid** control from the **Toolbox** to the design surface for your application, assumed here to be `Form1`.</span></span>  
  
     <span data-ttu-id="2fd32-119">Der Standardname für das Steuerelement des Eigenschaftenrasters ist `PropertyGrid1`.</span><span class="sxs-lookup"><span data-stu-id="2fd32-119">The default name of the property-grid control is `PropertyGrid1`.</span></span>  
  
2.  <span data-ttu-id="2fd32-120">Doppelklicken Sie auf die Entwurfsoberfläche für `Form1`, um den Code für den Ereignishandler zum Laden von Formularen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2fd32-120">Double-click the design surface for `Form1` to open the code for the form-load event handler.</span></span>  
  
3.  <span data-ttu-id="2fd32-121">Legen Sie das `My.Settings`-Objekt als ausgewähltes Objekt für das Eigenschaftenraster fest.</span><span class="sxs-lookup"><span data-stu-id="2fd32-121">Set the `My.Settings` object as the selected object for the property grid.</span></span>  
  
     <span data-ttu-id="2fd32-122">[!code-vb[VbVbalrMyResources#11](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2fd32-122">[!code-vb[VbVbalrMyResources#11](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_1.vb)]</span></span>  
  
4.  <span data-ttu-id="2fd32-123">Konfigurieren Sie das Eigenschaftenraster so, dass nur die Benutzereinstellungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2fd32-123">Configure the property grid to show only the user settings.</span></span>  
  
     <span data-ttu-id="2fd32-124">[!code-vb[VbVbalrMyResources#12](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2fd32-124">[!code-vb[VbVbalrMyResources#12](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_2.vb)]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fd32-125">Um nur die Einstellungen des Anwendungsbereichs anzuzeigen, verwenden Sie das <xref:System.Configuration.ApplicationScopedSettingAttribute>-Attribut anstelle von <xref:System.Configuration.UserScopedSettingAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2fd32-125">To show only the application-scope settings, use the <xref:System.Configuration.ApplicationScopedSettingAttribute> attribute instead of  <xref:System.Configuration.UserScopedSettingAttribute>.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2fd32-126">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="2fd32-126">Robust Programming</span></span>  
 <span data-ttu-id="2fd32-127">Die Anwendung speichert die Benutzereinstellungen beim Herunterfahren der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2fd32-127">The application saves the user settings when the application shuts down.</span></span> <span data-ttu-id="2fd32-128">Um die Einstellungen sofort zu speichern, rufen Sie die `My.Settings.Save`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="2fd32-128">To save the settings immediately, call the `My.Settings.Save` method.</span></span> <span data-ttu-id="2fd32-129">Weitere Informationen finden Sie unter [Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2fd32-129">For more information, see [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fd32-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fd32-130">See Also</span></span>  
 <span data-ttu-id="2fd32-131">[My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span><span class="sxs-lookup"><span data-stu-id="2fd32-131">[My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span></span>  
 <span data-ttu-id="2fd32-132">[Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span><span class="sxs-lookup"><span data-stu-id="2fd32-132">[How to: Read Application Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span></span>  
 <span data-ttu-id="2fd32-133">[Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="2fd32-133">[How to: Change User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span></span>  
 <span data-ttu-id="2fd32-134">[Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="2fd32-134">[How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span></span>  
 [<span data-ttu-id="2fd32-135">Verwalten von Anwendungseinstellungen (.NET)</span><span class="sxs-lookup"><span data-stu-id="2fd32-135">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

