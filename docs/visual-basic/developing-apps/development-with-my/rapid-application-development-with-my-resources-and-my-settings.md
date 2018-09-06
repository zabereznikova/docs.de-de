---
title: Schnelle Anwendungsentwicklung mit My.Resources und My.Settings (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 7dbb15c43d044e21c9823c4a1652b0408006e5c3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44032766"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="9e89b-102">Schnelle Anwendungsentwicklung mit My.Resources und My.Settings (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e89b-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>
<span data-ttu-id="9e89b-103">Die `My.Resources` Objekt bietet Zugriff auf die Ressourcen der Anwendung und ermöglicht es Ihnen, Ressourcen für Ihre Anwendung dynamisch abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9e89b-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="9e89b-104">Abrufen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9e89b-104">Retrieving Resources</span></span>  
 <span data-ttu-id="9e89b-105">Eine Reihe von Ressourcen wie Audiodateien, Symbole, Bilder und Zeichenfolgen abgerufen werden kann, über die `My.Resources` Objekt.</span><span class="sxs-lookup"><span data-stu-id="9e89b-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="9e89b-106">Beispielsweise können Sie die Dateien der Anwendung kulturspezifische Ressource zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9e89b-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="9e89b-107">Im folgenden Beispiel wird das Symbol für das Formular auf das Symbol mit dem Namen `Form1Icon` in der Ressourcendatei der Anwendung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9e89b-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 <span data-ttu-id="9e89b-108">Die `My.Resources` -Objekt macht nur globale Ressourcen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e89b-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="9e89b-109">Er bietet Zugriff auf die Ressourcendateien, die Formularen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9e89b-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="9e89b-110">Sie müssen die Formularressourcen aus dem Formular zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9e89b-110">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="9e89b-111">Auf ähnliche Weise die `My.Settings` Objekt bietet Zugriff auf die Einstellungen der Anwendung und ermöglicht es Ihnen, dynamisch speichern und Abrufen von Eigenschaften und andere Informationen für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9e89b-111">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="9e89b-112">Weitere Informationen finden Sie unter [My.Resources-Objekt](../../../visual-basic/language-reference/objects/my-resources-object.md) und [My.Settings-Objekt](../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="9e89b-112">For more information, see [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) and [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e89b-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e89b-113">See Also</span></span>  
 [<span data-ttu-id="9e89b-114">My.Resources-Objekt</span><span class="sxs-lookup"><span data-stu-id="9e89b-114">My.Resources Object</span></span>](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [<span data-ttu-id="9e89b-115">My.Settings-Objekt</span><span class="sxs-lookup"><span data-stu-id="9e89b-115">My.Settings Object</span></span>](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [<span data-ttu-id="9e89b-116">Zugreifen auf Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="9e89b-116">Accessing Application Settings</span></span>](../../../visual-basic/developing-apps/programming/app-settings/index.md)
