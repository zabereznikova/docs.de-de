---
title: Hinzufügen eines Dienstverweises in einer Workflowprojektmappe
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 577026249e00b528cf5c6e7ccd9527e02cb22a28
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597669"
---
# <a name="add-a-service-reference-in-a-workflow-solution"></a>Hinzufügen eines Dienst Verweises in einer Workflow Projekt Mappe

Die Abläufe beim Hinzufügen eines Dienstverweises in einer Workflowanwendung unterscheiden sich geringfügig von denen bei einer standardmäßigen WCF-Anwendung. Wenn Sie **Add**  >  **Dienst Verweis** hinzufügen auswählen und die URL für den Dienst angeben, werden die Metadaten heruntergeladen, und es werden benutzerdefinierte Aktivitäten generiert, mit denen Sie den WCF-Dienst oder den WCF-Workflow Dienst abrufen können. Nach dem Hinzufügen eines Dienstverweises erstellen Sie die Projektmappe erneut, damit die generierten Aktivitäten erstellt werden. Die Aktivitäten werden in der Toolbox des Workflow-Designers angezeigt. Dies funktioniert nur, wenn Sie einen Dienst Verweis innerhalb einer Workflow Projekt Mappe hinzufügen. Im folgenden Webcast wird gezeigt, wie ein Dienst Verweis in anderen Projekttypen hinzugefügt wird: [Aufrufen eines WCF-Diensts aus einem Workflow in einem Webprojekt](https://docs.microsoft.com/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow).

Wenn Sie Diensten, die denselben Vorgangsnamen enthalten, zwei oder mehrere Dienstverweise hinzufügen, führt dies zu einem Problem. Die generierten Aktivitäten rufen nur den ersten Dienstvorgang auf. Um dieses Problem zu umgehen, benennen Sie die Dienst Vorgänge so um, dass Sie unterschiedlich sind, oder ändern Sie den Namen der Endpunkt Konfiguration in jeder generierten Aktivität.

## <a name="see-also"></a>Weitere Informationen

- [Workflowdienste](workflow-services.md)
- [Aufrufen eines WCF-Diensts von einem Workflow in einem Webprojekt](https://docs.microsoft.com/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)
