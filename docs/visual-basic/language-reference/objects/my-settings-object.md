---
title: My.Settings-Objekt | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
dev_langs:
- VB
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: 16
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4d6ee6d2d54c0e3a4af3b7cdec5f81166ce3ddce
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="mysettings-object"></a><span data-ttu-id="237fa-102">My.Settings-Objekt</span><span class="sxs-lookup"><span data-stu-id="237fa-102">My.Settings Object</span></span>
<span data-ttu-id="237fa-103">Stellt Eigenschaften und Methoden für den Zugriff auf die Einstellungen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="237fa-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="237fa-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="237fa-104">Remarks</span></span>  
 <span data-ttu-id="237fa-105">Das `My.Settings` -Objekt bietet Zugriff auf die Einstellungen der Anwendung und ermöglicht es Ihnen, dynamisch speichern und Abrufen von Eigenschaften und andere Informationen für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="237fa-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="237fa-106">Weitere Informationen finden Sie unter [Verwalten von Einstellungen (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="237fa-106">For more information, see [Managing Application Settings (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="237fa-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="237fa-107">Properties</span></span>  
 <span data-ttu-id="237fa-108">Die Eigenschaften der `My.Settings` Objekt ermöglichen den Zugriff auf die Einstellungen Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="237fa-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="237fa-109">Verwenden Sie zum Hinzufügen oder entfernen Sie die Einstellungen, die **Einstellungs-Designer**.</span><span class="sxs-lookup"><span data-stu-id="237fa-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="237fa-110">Jede Einstellung hat eine **Namen**, **Typ**, **Bereich**, und **Wert**, und diese Einstellungen bestimmen, wie diese Eigenschaft auf jede Einstellung in wird die `My.Settings` Objekt:</span><span class="sxs-lookup"><span data-stu-id="237fa-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
-   <span data-ttu-id="237fa-111">**Namen** bestimmt den Namen der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="237fa-111">**Name** determines the name of the property.</span></span>  
  
-   <span data-ttu-id="237fa-112">**Typ** bestimmt den Typ der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="237fa-112">**Type** determines the type of the property.</span></span>  
  
-   <span data-ttu-id="237fa-113">**Bereich** gibt an, ob die Eigenschaft schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="237fa-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="237fa-114">Wenn der Wert **Anwendung**, die Eigenschaft ist schreibgeschützt, wenn der Wert **Benutzer**, die Eigenschaft ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="237fa-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
-   <span data-ttu-id="237fa-115">**Wert** ist der Standardwert der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="237fa-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="237fa-116">Methoden</span><span class="sxs-lookup"><span data-stu-id="237fa-116">Methods</span></span>  
  
|<span data-ttu-id="237fa-117">Methode</span><span class="sxs-lookup"><span data-stu-id="237fa-117">Method</span></span>|<span data-ttu-id="237fa-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="237fa-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="237fa-119">Lädt die Einstellungen aus der zuletzt gespeicherten Werte.</span><span class="sxs-lookup"><span data-stu-id="237fa-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="237fa-120">Speichert die aktuellen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="237fa-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="237fa-121">Die `My.Settings` Objekt stellt auch erweiterte Eigenschaften und Methoden, die von der <xref:System.Configuration.ApplicationSettingsBase>Klasse</xref:System.Configuration.ApplicationSettingsBase> geerbt</span><span class="sxs-lookup"><span data-stu-id="237fa-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="237fa-122">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="237fa-122">Tasks</span></span>  
 <span data-ttu-id="237fa-123">Die folgende Tabelle enthält Beispiele für Aufgaben mit der `My.Settings` Objekt.</span><span class="sxs-lookup"><span data-stu-id="237fa-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="237fa-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="237fa-124">To</span></span>|<span data-ttu-id="237fa-125">Siehe</span><span class="sxs-lookup"><span data-stu-id="237fa-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="237fa-126">Lesen Sie eine anwendungseinstellung</span><span class="sxs-lookup"><span data-stu-id="237fa-126">Read an application setting</span></span>|[<span data-ttu-id="237fa-127">Gewusst wie: Lesen von Anwendungseinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="237fa-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="237fa-128">Ändern einer benutzereinstellung</span><span class="sxs-lookup"><span data-stu-id="237fa-128">Change a user setting</span></span>|[<span data-ttu-id="237fa-129">Gewusst wie: Ändern von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="237fa-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="237fa-130">Beibehalten von benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="237fa-130">Persist user settings</span></span>|[<span data-ttu-id="237fa-131">Gewusst wie: Beibehalten von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="237fa-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="237fa-132">Erstellen Sie ein Eigenschaftenraster für benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="237fa-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="237fa-133">Gewusst wie: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="237fa-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="237fa-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="237fa-134">Example</span></span>  
 <span data-ttu-id="237fa-135">In diesem Beispiel wird der Wert der `Nickname` Einstellung.</span><span class="sxs-lookup"><span data-stu-id="237fa-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 <span data-ttu-id="237fa-136">[!code-vb[VbVbalrMyResources&14;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="237fa-136">[!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]</span></span>  
  
 <span data-ttu-id="237fa-137">Für dieses Beispiel funktioniert, müssen die Anwendung eine `Nickname` -Einstellung vom Typ `String`.</span><span class="sxs-lookup"><span data-stu-id="237fa-137">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="237fa-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="237fa-138">See Also</span></span>  
 <span data-ttu-id="237fa-139"><xref:System.Configuration.ApplicationSettingsBase></xref:System.Configuration.ApplicationSettingsBase></span><span class="sxs-lookup"><span data-stu-id="237fa-139"><xref:System.Configuration.ApplicationSettingsBase></span></span>   
<span data-ttu-id="237fa-140"> [Gewusst wie: Lesen von Anwendungseinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span><span class="sxs-lookup"><span data-stu-id="237fa-140"> [How to: Read Application Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span></span>  
<span data-ttu-id="237fa-141"> [Gewusst wie: Ändern von Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="237fa-141"> [How to: Change User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span></span>  
<span data-ttu-id="237fa-142"> [Gewusst wie: Beibehalten von Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="237fa-142"> [How to: Persist User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span></span>  
<span data-ttu-id="237fa-143"> [Gewusst wie: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="237fa-143"> [How to: Create Property Grids for User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span></span>  
<span data-ttu-id="237fa-144"> [Verwalten von Anwendungseinstellungen (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)</span><span class="sxs-lookup"><span data-stu-id="237fa-144"> [Managing Application Settings (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)</span></span>
