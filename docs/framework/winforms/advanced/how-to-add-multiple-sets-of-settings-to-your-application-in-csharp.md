---
title: 'Vorgehensweise: Hinzufügen mehrerer Gruppen von Einstellungen zur Anwendung in C#'
description: Erfahren Sie, wie Sie Ihrer Anwendung in c# mithilfe von Visual Studio mehrere Sätze von Windows Forms Einstellungen hinzufügen.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 579374ff101758b3224bc122c46b891280ed2609
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173444"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="2de67-103">Gewusst wie: Hinzufügen mehrerer Einstellungs Sätze zu Ihrer Anwendung in C\#</span><span class="sxs-lookup"><span data-stu-id="2de67-103">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>

<span data-ttu-id="2de67-104">In einigen Fällen möchten Sie möglicherweise mehrere Einstellungs Sätze in einer Anwendung haben.</span><span class="sxs-lookup"><span data-stu-id="2de67-104">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="2de67-105">Wenn Sie z. b. eine Anwendung entwickeln, in der eine bestimmte Gruppe von Einstellungen häufig geändert werden soll, kann es ratsam sein, Sie in eine einzelne Datei aufzuteilen, damit die Datei im Einzelhandel ersetzt werden kann, sodass andere Einstellungen nicht betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="2de67-105">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="2de67-106">Mit Visual Studio können Sie Ihrem Projekt mehrere Einstellungs Sätze hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2de67-106">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="2de67-107">Auf zusätzliche Einstellungs Sätze kann über das-Objekt zugegriffen werden `Properties.Settings` .</span><span class="sxs-lookup"><span data-stu-id="2de67-107">Additional sets of settings can be accessed via the `Properties.Settings` object.</span></span>

## <a name="add-an-additional-set-of-settings"></a><span data-ttu-id="2de67-108">Zusätzlichen Einstellungs Satz hinzufügen</span><span class="sxs-lookup"><span data-stu-id="2de67-108">Add an Additional Set of Settings</span></span>

1. <span data-ttu-id="2de67-109">Wählen Sie in Visual Studio im Menü **Projekt** die Option **Neues Element hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="2de67-109">In Visual Studio, from the **Project** menu, choose **Add New Item**.</span></span>

   <span data-ttu-id="2de67-110">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2de67-110">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="2de67-111">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Einstellungsdatei**aus, geben Sie einen Namen für die Datei ein, und klicken Sie auf **Hinzufügen** , um der Projekt Mappe eine neue Einstellungsdatei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2de67-111">In the **Add New Item** dialog box, select **Settings File**, enter a name for the file, and click **Add** to add a new settings file to your solution.</span></span>

3. <span data-ttu-id="2de67-112">Ziehen Sie die neue Einstellungsdatei in **Projektmappen-Explorer**in den Ordner **Properties** .</span><span class="sxs-lookup"><span data-stu-id="2de67-112">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="2de67-113">Dadurch können Ihre neuen Einstellungen im Code verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="2de67-113">This allows your new settings to be available in code.</span></span>

4. <span data-ttu-id="2de67-114">Fügen Sie die Einstellungen in dieser Datei hinzu, und verwenden Sie Sie wie jede andere Einstellungsdatei.</span><span class="sxs-lookup"><span data-stu-id="2de67-114">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="2de67-115">Sie können über das-Objekt auf diese Gruppe von Einstellungen zugreifen `Properties.Settings` .</span><span class="sxs-lookup"><span data-stu-id="2de67-115">You can access this group of settings via the `Properties.Settings` object.</span></span>

## <a name="see-also"></a><span data-ttu-id="2de67-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2de67-116">See also</span></span>

- [<span data-ttu-id="2de67-117">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="2de67-117">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="2de67-118">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="2de67-118">Application Settings Overview</span></span>](application-settings-overview.md)
