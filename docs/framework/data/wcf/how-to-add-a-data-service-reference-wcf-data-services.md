---
title: 'Vorgehensweise: Hinzufügen eines Datendienst Verweises (WCF Data Services)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: 42d89cf87b5fe9bbdb229f10cd6a0e340d4c08fd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790741"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>Vorgehensweise: Hinzufügen eines Datendienst Verweises (WCF Data Services)

Sie können das Dialogfeld " **Dienstverweis hinzufügen** " in Visual Studio verwenden, um einen Verweis auf WCF Data Services hinzuzufügen. Dies erleichtert Ihnen den Zugriff auf einen Datendienst in einer Clientanwendung, den Sie in Visual Studio entwickeln. Wenn Sie diese Prozedur ausführen, werden Datenklassen auf Grundlage von aus dem Datendienst abgerufenen Metadaten generiert. Weitere Informationen finden Sie unter [Erstellen der Datendienst-Client Bibliothek](generating-the-data-service-client-library-wcf-data-services.md).

## <a name="add-a-data-service-reference"></a>Hinzufügen eines Datendienst Verweises

1. (Optional) Wenn der Datendienst kein Teil der Projektmappe ist und nicht bereits ausgeführt ist, starten Sie den Datendienst und notieren Sie den URI des Datendiensts.

2. Klicken Sie in Visual Studio in **Projektmappen-Explorer**mit der rechten Maustaste auf das Client Projekt, und wählen Sie dann**Dienst Verweis** **Hinzufügen** > aus.

3. Wenn der Datendienst Teil der aktuellen Lösung ist, klicken Sie auf **ermitteln**.

     -oder-

     Geben Sie im Textfeld **Adresse** die Basis-URL des Daten Dienstanbieter ein, `http://localhost:1234/Northwind.svc`z. b., und klicken Sie dann auf **Gehe**zu.

4. Klicken Sie auf **OK**.

     Eine neue Codedatei, die die Daten Klassen enthält, die auf Datendienst Ressourcen zugreifen und diese interagieren können, wird dem Projekt hinzugefügt.

## <a name="see-also"></a>Siehe auch

- [Schnellstart](quickstart-wcf-data-services.md)
