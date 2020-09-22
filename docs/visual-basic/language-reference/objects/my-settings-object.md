---
title: My.Settings-Objekt
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: f3348e9eea5bdd7f4fd911150877c9aefdd66bcc
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867299"
---
# <a name="mysettings-object"></a><span data-ttu-id="11cc9-102">My.Settings-Objekt</span><span class="sxs-lookup"><span data-stu-id="11cc9-102">My.Settings Object</span></span>

<span data-ttu-id="11cc9-103">Stellt Eigenschaften und Methoden für den Zugriff auf die Einstellungen der Anwendung bereit.</span><span class="sxs-lookup"><span data-stu-id="11cc9-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11cc9-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="11cc9-104">Remarks</span></span>  

 <span data-ttu-id="11cc9-105">Das `My.Settings` -Objekt bietet Zugriff auf die Einstellungen der Anwendung und ermöglicht das dynamische Speichern und Abrufen von Eigenschafts Einstellungen und anderen Informationen für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="11cc9-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="11cc9-106">Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="11cc9-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="11cc9-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="11cc9-107">Properties</span></span>  

 <span data-ttu-id="11cc9-108">Die Eigenschaften des `My.Settings`-Objekts ermöglichen den Zugriff auf die Einstellungen Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="11cc9-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="11cc9-109">Verwenden Sie den **Einstellungs-Designer**, um Einstellungen hinzuzufügen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="11cc9-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="11cc9-110">Jede Einstellung hat einen **Namen**, einen **Typ**, einen **Bereich**und einen **Wert**, und diese Einstellungen bestimmen, wie die Eigenschaft für den Zugriff auf die einzelnen Einstellungen im Objekt angezeigt wird `My.Settings` :</span><span class="sxs-lookup"><span data-stu-id="11cc9-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
- <span data-ttu-id="11cc9-111">**Name** bestimmt den Namen der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="11cc9-111">**Name** determines the name of the property.</span></span>  
  
- <span data-ttu-id="11cc9-112">**Typ** bestimmt den Typ der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="11cc9-112">**Type** determines the type of the property.</span></span>  
  
- <span data-ttu-id="11cc9-113">Der **Bereich** gibt an, ob die Eigenschaft schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="11cc9-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="11cc9-114">Wenn der Wert " **Application**" ist, ist die Eigenschaft schreibgeschützt. Wenn der Wert **User**ist, lautet die Eigenschaft mit Lese-/Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="11cc9-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
- <span data-ttu-id="11cc9-115">**Value** ist der Standardwert der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="11cc9-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="11cc9-116">Methoden</span><span class="sxs-lookup"><span data-stu-id="11cc9-116">Methods</span></span>  
  
|<span data-ttu-id="11cc9-117">Methode</span><span class="sxs-lookup"><span data-stu-id="11cc9-117">Method</span></span>|<span data-ttu-id="11cc9-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="11cc9-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="11cc9-119">Lädt die Benutzereinstellungen aus den letzten gespeicherten Werten erneut.</span><span class="sxs-lookup"><span data-stu-id="11cc9-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="11cc9-120">Speichert die aktuellen Benutzereinstellungen.</span><span class="sxs-lookup"><span data-stu-id="11cc9-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="11cc9-121">Das `My.Settings` -Objekt stellt auch erweiterte Eigenschaften und Methoden bereit, die von der-Klasse geerbt wurden <xref:System.Configuration.ApplicationSettingsBase> .</span><span class="sxs-lookup"><span data-stu-id="11cc9-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="11cc9-122">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="11cc9-122">Tasks</span></span>  

 <span data-ttu-id="11cc9-123">In der folgenden Tabelle sind Beispiele für Aufgaben aufgeführt, die das- `My.Settings` Objekt betreffen.</span><span class="sxs-lookup"><span data-stu-id="11cc9-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="11cc9-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11cc9-124">To</span></span>|<span data-ttu-id="11cc9-125">Siehe</span><span class="sxs-lookup"><span data-stu-id="11cc9-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="11cc9-126">Anwendungs Einstellung lesen</span><span class="sxs-lookup"><span data-stu-id="11cc9-126">Read an application setting</span></span>|[<span data-ttu-id="11cc9-127">How to: Lesen von Anwendungseinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11cc9-127">How to: Read Application Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="11cc9-128">Ändern einer Benutzereinstellung</span><span class="sxs-lookup"><span data-stu-id="11cc9-128">Change a user setting</span></span>|[<span data-ttu-id="11cc9-129">How to: Ändern von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11cc9-129">How to: Change User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="11cc9-130">Beibehalten von Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="11cc9-130">Persist user settings</span></span>|[<span data-ttu-id="11cc9-131">How to: Beibehalten von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11cc9-131">How to: Persist User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="11cc9-132">Erstellen eines Eigenschaften Rasters für Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="11cc9-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="11cc9-133">How to: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11cc9-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="11cc9-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="11cc9-134">Example</span></span>  

 <span data-ttu-id="11cc9-135">In diesem Beispiel wird der Wert der `Nickname`-Einstellung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11cc9-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="11cc9-136">Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `Nickname`-Einstellung vom Typ `String` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="11cc9-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11cc9-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11cc9-137">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- [<span data-ttu-id="11cc9-138">How to: Lesen von Anwendungseinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11cc9-138">How to: Read Application Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="11cc9-139">How to: Ändern von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11cc9-139">How to: Change User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="11cc9-140">How to: Beibehalten von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11cc9-140">How to: Persist User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="11cc9-141">How to: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11cc9-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="11cc9-142">Verwalten von Anwendungseinstellungen (.NET)</span><span class="sxs-lookup"><span data-stu-id="11cc9-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
