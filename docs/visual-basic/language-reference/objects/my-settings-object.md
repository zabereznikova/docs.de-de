---
title: My.Settings-Objekt
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f744460f8ea6c6c7f5c8c5e1658bd357e910def
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mysettings-object"></a><span data-ttu-id="abec9-102">My.Settings-Objekt</span><span class="sxs-lookup"><span data-stu-id="abec9-102">My.Settings Object</span></span>
<span data-ttu-id="abec9-103">Stellt Eigenschaften und Methoden für den Zugriff auf die Einstellungen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="abec9-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abec9-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="abec9-104">Remarks</span></span>  
 <span data-ttu-id="abec9-105">Die `My.Settings` Objekt ermöglicht den Zugriff auf die Einstellungen der Anwendung, und lassen sich dynamisch speichern und Abrufen von Einstellungen und andere Informationen für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="abec9-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="abec9-106">Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="abec9-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="abec9-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="abec9-107">Properties</span></span>  
 <span data-ttu-id="abec9-108">Die Eigenschaften des `My.Settings`-Objekts ermöglichen den Zugriff auf die Einstellungen Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="abec9-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="abec9-109">Verwenden Sie zum Hinzufügen oder entfernen Sie die Einstellungen, die **Einstellungs-Designer**.</span><span class="sxs-lookup"><span data-stu-id="abec9-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="abec9-110">Jede Einstellung hat eine **Namen**, **Typ**, **Bereich**, und **Wert**, und diese Einstellungen bestimmen wie die einzelnen Einstellungen aufzurufende Eigenschaft wird angezeigt, der `My.Settings` Objekt:</span><span class="sxs-lookup"><span data-stu-id="abec9-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
-   <span data-ttu-id="abec9-111">**Namen** bestimmt den Namen der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="abec9-111">**Name** determines the name of the property.</span></span>  
  
-   <span data-ttu-id="abec9-112">**Typ** bestimmt den Typ der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="abec9-112">**Type** determines the type of the property.</span></span>  
  
-   <span data-ttu-id="abec9-113">**Bereich** gibt an, ob die Eigenschaft schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="abec9-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="abec9-114">Wenn der Wert **Anwendung**, die Eigenschaft ist schreibgeschützt; Wenn der Wert **Benutzer**, die Eigenschaft ist Lese-/ Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="abec9-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
-   <span data-ttu-id="abec9-115">**Wert** ist der Standardwert der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="abec9-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="abec9-116">Methoden</span><span class="sxs-lookup"><span data-stu-id="abec9-116">Methods</span></span>  
  
|<span data-ttu-id="abec9-117">Methode</span><span class="sxs-lookup"><span data-stu-id="abec9-117">Method</span></span>|<span data-ttu-id="abec9-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="abec9-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="abec9-119">Lädt die benutzereinstellungen aus dem zuletzt gespeicherten Werte.</span><span class="sxs-lookup"><span data-stu-id="abec9-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="abec9-120">Speichert den aktuellen Einstellungen des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="abec9-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="abec9-121">Die `My.Settings` Objekt stellt auch erweiterte Eigenschaften und Methoden, geerbt von der <xref:System.Configuration.ApplicationSettingsBase> Klasse.</span><span class="sxs-lookup"><span data-stu-id="abec9-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="abec9-122">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="abec9-122">Tasks</span></span>  
 <span data-ttu-id="abec9-123">Die folgende Tabelle enthält Beispiele für Aufgaben im Zusammenhang mit der `My.Settings` Objekt.</span><span class="sxs-lookup"><span data-stu-id="abec9-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="abec9-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="abec9-124">To</span></span>|<span data-ttu-id="abec9-125">Siehe</span><span class="sxs-lookup"><span data-stu-id="abec9-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="abec9-126">Eine anwendungseinstellung lesen</span><span class="sxs-lookup"><span data-stu-id="abec9-126">Read an application setting</span></span>|[<span data-ttu-id="abec9-127">Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="abec9-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="abec9-128">Ändern einer benutzereinstellung</span><span class="sxs-lookup"><span data-stu-id="abec9-128">Change a user setting</span></span>|[<span data-ttu-id="abec9-129">Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="abec9-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="abec9-130">Beibehalten von benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="abec9-130">Persist user settings</span></span>|[<span data-ttu-id="abec9-131">Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="abec9-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="abec9-132">Erstellen Sie eine Eigenschaftenraster für benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="abec9-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="abec9-133">Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="abec9-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="abec9-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="abec9-134">Example</span></span>  
 <span data-ttu-id="abec9-135">In diesem Beispiel wird der Wert der `Nickname`-Einstellung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="abec9-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]  
  
 <span data-ttu-id="abec9-136">Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `Nickname`-Einstellung vom Typ `String` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="abec9-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abec9-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abec9-137">See Also</span></span>  
 <xref:System.Configuration.ApplicationSettingsBase>  
 [<span data-ttu-id="abec9-138">Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="abec9-138">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [<span data-ttu-id="abec9-139">Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="abec9-139">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [<span data-ttu-id="abec9-140">Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="abec9-140">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [<span data-ttu-id="abec9-141">Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="abec9-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [<span data-ttu-id="abec9-142">Verwalten von Anwendungseinstellungen (.NET)</span><span class="sxs-lookup"><span data-stu-id="abec9-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
