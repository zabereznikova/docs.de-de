---
title: Schnelle Anwendungsentwicklung mit My.Resources und My.Settings (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1657febf935560ff4c8dd2f54b10fdcb2254891f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="8c767-102">Schnelle Anwendungsentwicklung mit My.Resources und My.Settings (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c767-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>
<span data-ttu-id="8c767-103">Die `My.Resources` -Objekt ermöglicht den Zugriff auf die Ressourcen der Anwendung und ermöglicht Ihnen, Ressourcen für Ihre Anwendung dynamisch abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8c767-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="8c767-104">Abrufen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="8c767-104">Retrieving Resources</span></span>  
 <span data-ttu-id="8c767-105">Eine Reihe von Ressourcen wie Audiodateien, Symbole, Bilder und Zeichenfolgen abgerufen werden kann, über die `My.Resources` Objekt.</span><span class="sxs-lookup"><span data-stu-id="8c767-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="8c767-106">Beispielsweise können Sie die Anwendung kulturspezifische Ressourcendateien zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8c767-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="8c767-107">Im folgenden Beispiel wird das Symbol des Formulars auf das Symbol mit dem Namen `Form1Icon` in der Anwendung Ressourcendatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8c767-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 <span data-ttu-id="8c767-108">Die `My.Resources` Objekt macht nur globale Ressourcen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8c767-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="8c767-109">Es stellt nicht den Zugriff auf Formularen zugeordnete Ressourcendateien bereit.</span><span class="sxs-lookup"><span data-stu-id="8c767-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="8c767-110">Sie müssen die Formularressourcen aus dem Formular zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8c767-110">You must access the form resources from the form.</span></span> <span data-ttu-id="8c767-111">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5).</span><span class="sxs-lookup"><span data-stu-id="8c767-111">For more information, see [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5).</span></span>  
  
 <span data-ttu-id="8c767-112">Auf ähnliche Weise die `My.Settings` Objekt ermöglicht den Zugriff auf die Einstellungen der Anwendung, und lassen sich dynamisch speichern und Abrufen von Einstellungen und andere Informationen für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8c767-112">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="8c767-113">Weitere Informationen finden Sie unter [My.Resources-Objekt](../../../visual-basic/language-reference/objects/my-resources-object.md) und [My.Settings-Objekt](../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="8c767-113">For more information, see [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) and [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c767-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c767-114">See Also</span></span>  
 [<span data-ttu-id="8c767-115">My.Resources-Objekt</span><span class="sxs-lookup"><span data-stu-id="8c767-115">My.Resources Object</span></span>](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [<span data-ttu-id="8c767-116">My.Settings-Objekt</span><span class="sxs-lookup"><span data-stu-id="8c767-116">My.Settings Object</span></span>](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [<span data-ttu-id="8c767-117">Zugreifen auf Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="8c767-117">Accessing Application Settings</span></span>](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)
