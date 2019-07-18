---
title: Hinzufügen eines Dienstverweises in einer Workflowprojektmappe
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 8f1fa4604f1a1873c7063ec3c9dccf08bd0aa0ee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669666"
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a>Hinzufügen eines Dienstverweises in einer Workflowprojektmappe

Die Abläufe beim Hinzufügen eines Dienstverweises in einer Workflowanwendung unterscheiden sich geringfügig von denen bei einer standardmäßigen WCF-Anwendung. Bei der Auswahl **hinzufügen > Dienstverweis** und geben Sie die URL an den Dienst, die Metadaten heruntergeladen und benutzerdefinierte Aktivitäten generiert, mit denen Sie rufen die WCF-Dienst oder die WCF-Workflowdienst, die Sie hinzugefügt haben, einen Verweis auf. Nach dem Hinzufügen eines Dienstverweises erstellen Sie die Projektmappe erneut, damit die generierten Aktivitäten erstellt werden. Die Aktivitäten werden in der Toolbox des Workflow-Designers angezeigt. Diese Vorgehensweise funktioniert jedoch nur, wenn Sie einen Dienstverweis innerhalb einer Workflowprojektmappe erstellen. Im Webcast wird das Hinzufügen eines Dienstverweises in anderen Projekttypen veranschaulicht: [Aufrufen eines WCF-Diensts aus einem Workflow in einem Webprojekt](https://go.microsoft.com/fwlink/?LinkId=207725).

Wenn Sie Diensten, die denselben Vorgangsnamen enthalten, zwei oder mehrere Dienstverweise hinzufügen, führt dies zu einem Problem. Die generierten Aktivitäten rufen nur den ersten Dienstvorgang auf. Sie können dieses Problem umgehen, indem Sie die Dienstvorgänge entsprechend umbenennen oder den Namen der Endpunktkonfiguration in jeder generierten Aktivität ändern.

## <a name="see-also"></a>Siehe auch

- [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Aufrufen eines WCF-Diensts aus einem Workflow in einem Webprojekt](https://go.microsoft.com/fwlink/?LinkId=207725)
