---
title: 'Vorgehensweise: Hinzufügen mehrerer Gruppen von Einstellungen zur Anwendung in C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: c6842d11c04e905d42734af939f2c3f0cfeacd47
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040124"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="b06c7-102">Vorgehensweise: Fügen Sie Ihrer Anwendung mehrere Einstellungs Sätze in C hinzu.\#</span><span class="sxs-lookup"><span data-stu-id="b06c7-102">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>

<span data-ttu-id="b06c7-103">In einigen Fällen möchten Sie möglicherweise mehrere Einstellungs Sätze in einer Anwendung haben.</span><span class="sxs-lookup"><span data-stu-id="b06c7-103">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="b06c7-104">Wenn Sie z. b. eine Anwendung entwickeln, in der eine bestimmte Gruppe von Einstellungen häufig geändert werden soll, kann es ratsam sein, Sie in eine einzelne Datei aufzuteilen, damit die Datei im Einzelhandel ersetzt werden kann, sodass andere Einstellungen nicht betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="b06c7-104">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="b06c7-105">Mit Visual Studio können Sie Ihrem Projekt mehrere Einstellungs Sätze hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b06c7-105">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="b06c7-106">Auf zusätzliche Einstellungs Sätze kann über das `Properties.Settings` -Objekt zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="b06c7-106">Additional sets of settings can be accessed via the `Properties.Settings` object.</span></span>

## <a name="add-an-additional-set-of-settings"></a><span data-ttu-id="b06c7-107">Zusätzlichen Einstellungs Satz hinzufügen</span><span class="sxs-lookup"><span data-stu-id="b06c7-107">Add an Additional Set of Settings</span></span>

1. <span data-ttu-id="b06c7-108">Wählen Sie in Visual Studio im Menü **Projekt** die Option **Neues Element hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="b06c7-108">In Visual Studio, from the **Project** menu, choose **Add New Item**.</span></span>

   <span data-ttu-id="b06c7-109">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b06c7-109">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="b06c7-110">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Einstellungsdatei**aus, geben Sie einen Namen für die Datei ein, und klicken Sie auf **Hinzufügen** , um der Projekt Mappe eine neue Einstellungsdatei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b06c7-110">In the **Add New Item** dialog box, select **Settings File**, enter a name for the file, and click **Add** to add a new settings file to your solution.</span></span>

3. <span data-ttu-id="b06c7-111">Ziehen Sie die neue Einstellungsdatei in **Projektmappen-Explorer**in den Ordner **Properties** .</span><span class="sxs-lookup"><span data-stu-id="b06c7-111">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="b06c7-112">Dadurch können Ihre neuen Einstellungen im Code verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="b06c7-112">This allows your new settings to be available in code.</span></span>

4. <span data-ttu-id="b06c7-113">Fügen Sie die Einstellungen in dieser Datei hinzu, und verwenden Sie Sie wie jede andere Einstellungsdatei.</span><span class="sxs-lookup"><span data-stu-id="b06c7-113">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="b06c7-114">Sie können über das `Properties.Settings` -Objekt auf diese Gruppe von Einstellungen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b06c7-114">You can access this group of settings via the `Properties.Settings` object.</span></span>

## <a name="see-also"></a><span data-ttu-id="b06c7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b06c7-115">See also</span></span>

- [<span data-ttu-id="b06c7-116">Verwenden von Anwendungseinstellungen und Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="b06c7-116">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="b06c7-117">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="b06c7-117">Application Settings Overview</span></span>](application-settings-overview.md)
