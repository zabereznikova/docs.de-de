---
title: 'Vorgehensweise: Erstellen einer neuen Einstellung zur Entwurfszeit'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: 35a7cd8cc1daaf76a25977751ddc9ec0709e5947
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037906"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="628c8-102">Vorgehensweise: Erstellen einer neuen Einstellung zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="628c8-102">How To: Create a new setting at design time</span></span>

<span data-ttu-id="628c8-103">Sie können eine neue Einstellung zur Entwurfszeit erstellen, indem Sie den Einstellungs-Designer in Visual Studio verwenden.</span><span class="sxs-lookup"><span data-stu-id="628c8-103">You can create a new setting at design time by using the Settings designer in Visual Studio.</span></span> <span data-ttu-id="628c8-104">Der Einstellungs-Designer ist eine Schnittstelle im Raster Stil, mit der Sie neue Einstellungen erstellen und Eigenschaften für diese Einstellungen angeben können.</span><span class="sxs-lookup"><span data-stu-id="628c8-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="628c8-105">Sie müssen Name, Wert, Typ und Bereich für die neuen Einstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="628c8-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="628c8-106">Nachdem eine Einstellung erstellt wurde, können Sie im Code darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="628c8-106">Once a setting is created, it is accessible in code.</span></span>

## <a name="create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="628c8-107">Erstellen einer neuen Einstellung zur Entwurfszeit in C\#</span><span class="sxs-lookup"><span data-stu-id="628c8-107">Create a new setting at design time in C\#</span></span>

1. <span data-ttu-id="628c8-108">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="628c8-108">Open Visual Studio.</span></span>

2. <span data-ttu-id="628c8-109">Erweitern Sie in **Projektmappen-Explorer**den Knoten **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="628c8-109">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>

3. <span data-ttu-id="628c8-110">Doppelklicken Sie auf die Einstellungsdatei, der Sie eine neue Einstellung hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="628c8-110">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="628c8-111">Der Standardname für diese Datei ist Settings. Settings.</span><span class="sxs-lookup"><span data-stu-id="628c8-111">The default name for this file is Settings.settings.</span></span>

4. <span data-ttu-id="628c8-112">Legen Sie im Einstellungs-Designer den **Namen**, den **Wert**, den **Typ**und den Gültigkeits **Bereich** für die Einstellung fest.</span><span class="sxs-lookup"><span data-stu-id="628c8-112">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="628c8-113">Jede Zeile stellt eine einzelne Einstellung dar.</span><span class="sxs-lookup"><span data-stu-id="628c8-113">Each row represents a single setting.</span></span>

## <a name="create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="628c8-114">Erstellen Sie eine neue Einstellung zur Entwurfszeit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="628c8-114">Create a new setting at design time in Visual Basic</span></span>

1. <span data-ttu-id="628c8-115">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="628c8-115">Open Visual Studio.</span></span>

2. <span data-ttu-id="628c8-116">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Projekt Knoten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="628c8-116">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>

3. <span data-ttu-id="628c8-117">Wählen Sie auf der Seite **Eigenschaften** die Registerkarte **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="628c8-117">In the **Properties** page, select the **Settings** tab.</span></span>

4. <span data-ttu-id="628c8-118">Legen Sie im Einstellungs-Designer den **Namen**, den **Wert**, den **Typ**und den Gültigkeits **Bereich** für die Einstellung fest.</span><span class="sxs-lookup"><span data-stu-id="628c8-118">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="628c8-119">Jede Zeile stellt eine einzelne Einstellung dar.</span><span class="sxs-lookup"><span data-stu-id="628c8-119">Each row represents a single setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="628c8-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="628c8-120">See also</span></span>

- [<span data-ttu-id="628c8-121">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="628c8-121">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="628c8-122">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="628c8-122">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="628c8-123">How To: Ändern des Werts einer vorhandenen Einstellung zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="628c8-123">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
