---
title: 'Gewusst wie: Hinzufügen eines Datendienstverweises (WCF Data Services)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: fc1786e1c6102c702374989253cd3ce23e3f7b54
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43404422"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>Gewusst wie: Hinzufügen ein Datendienstverweises (WCF Data Services)

Sie können die **Hinzufügen eines Dienstverweises** Dialogfeld in Visual Studio zum Hinzufügen eines Verweises auf WCF Data Services. Dies erleichtert Ihnen den Zugriff auf einen Datendienst in einer Clientanwendung, den Sie in Visual Studio entwickeln. Wenn Sie diese Prozedur ausführen, werden Datenklassen auf Grundlage von aus dem Datendienst abgerufenen Metadaten generiert. Weitere Informationen finden Sie unter [Generieren der Datendienst-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).

## <a name="add-a-data-service-reference"></a>Hinzufügen eines Datendienstverweises

1. (Optional) Wenn der Datendienst kein Teil der Projektmappe ist und nicht bereits ausgeführt ist, starten Sie den Datendienst und notieren Sie den URI des Datendiensts.

2. In Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Clientprojekt, und wählen Sie dann **hinzufügen** > **Dienstverweis**.

3. Wenn der Datendienst Teil der aktuellen Projektmappe ist, klicken Sie auf **Discover**.

     - oder - 

     In der **Adresse** Textfeld die base-URL des Datendiensts, z. B. `http://localhost:1234/Northwind.svc`, und klicken Sie dann auf **wechseln**.

4. Klicken Sie auf **OK**.

     Eine neue Codedatei, die die Datenklassen enthält, die Zugriff auf und Interaktion mit datendienstressourcen können wird dem Projekt hinzugefügt.

## <a name="see-also"></a>Siehe auch

- [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)