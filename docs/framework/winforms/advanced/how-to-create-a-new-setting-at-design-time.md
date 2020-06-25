---
title: 'Vorgehensweise: Erstellen einer neuen Einstellung zur Entwurfszeit'
description: Erfahren Sie, wie Sie eine neue Windows Forms Einstellung zur Entwurfszeit mithilfe des Einstellungs-Designers in Visual Studio erstellen.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: ce37b42191999e29de2f2f7f7e7abfa0ec3f4d47
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325847"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="fe8e8-103">Gewusst wie: Erstellen einer neuen Einstellung zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="fe8e8-103">How To: Create a new setting at design time</span></span>

<span data-ttu-id="fe8e8-104">Sie können eine neue Einstellung zur Entwurfszeit erstellen, indem Sie den Einstellungs-Designer in Visual Studio verwenden.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-104">You can create a new setting at design time by using the Settings designer in Visual Studio.</span></span> <span data-ttu-id="fe8e8-105">Der Einstellungs-Designer ist eine Schnittstelle im Raster Stil, mit der Sie neue Einstellungen erstellen und Eigenschaften für diese Einstellungen angeben können.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-105">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="fe8e8-106">Sie müssen Name, Wert, Typ und Bereich für die neuen Einstellungen angeben.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-106">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="fe8e8-107">Nachdem eine Einstellung erstellt wurde, können Sie im Code darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-107">Once a setting is created, it is accessible in code.</span></span>

## <a name="create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="fe8e8-108">Erstellen einer neuen Einstellung zur Entwurfszeit in C\#</span><span class="sxs-lookup"><span data-stu-id="fe8e8-108">Create a new setting at design time in C\#</span></span>

1. <span data-ttu-id="fe8e8-109">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-109">Open Visual Studio.</span></span>

2. <span data-ttu-id="fe8e8-110">Erweitern Sie in **Projektmappen-Explorer**den Knoten **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-110">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>

3. <span data-ttu-id="fe8e8-111">Doppelklicken Sie auf die Einstellungsdatei, der Sie eine neue Einstellung hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-111">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="fe8e8-112">Der Standardname für diese Datei ist Settings. Settings.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-112">The default name for this file is Settings.settings.</span></span>

4. <span data-ttu-id="fe8e8-113">Legen Sie im Einstellungs-Designer den **Namen**, den **Wert**, den **Typ**und den Gültigkeits **Bereich** für die Einstellung fest.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-113">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="fe8e8-114">Jede Zeile stellt eine einzelne Einstellung dar.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-114">Each row represents a single setting.</span></span>

## <a name="create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="fe8e8-115">Erstellen Sie eine neue Einstellung zur Entwurfszeit in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fe8e8-115">Create a new setting at design time in Visual Basic</span></span>

1. <span data-ttu-id="fe8e8-116">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-116">Open Visual Studio.</span></span>

2. <span data-ttu-id="fe8e8-117">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Projekt Knoten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-117">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>

3. <span data-ttu-id="fe8e8-118">Wählen Sie auf der Seite **Eigenschaften** die Registerkarte **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-118">In the **Properties** page, select the **Settings** tab.</span></span>

4. <span data-ttu-id="fe8e8-119">Legen Sie im Einstellungs-Designer den **Namen**, den **Wert**, den **Typ**und den Gültigkeits **Bereich** für die Einstellung fest.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-119">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="fe8e8-120">Jede Zeile stellt eine einzelne Einstellung dar.</span><span class="sxs-lookup"><span data-stu-id="fe8e8-120">Each row represents a single setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe8e8-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe8e8-121">See also</span></span>

- [<span data-ttu-id="fe8e8-122">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="fe8e8-122">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="fe8e8-123">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="fe8e8-123">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="fe8e8-124">Vorgehensweise: Ändern des Werts einer vorhandenen Einstellung zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="fe8e8-124">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
