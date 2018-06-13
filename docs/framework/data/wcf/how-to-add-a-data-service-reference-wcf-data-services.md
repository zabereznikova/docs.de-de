---
title: 'Gewusst wie: Hinzufügen eines Datendienstverweises (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: a8dcc01fb7a564a363cabed6a22738cd520d317f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356230"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>Gewusst wie: Hinzufügen eines Datendienstverweises (WCF Data Services)
Sie können die **Hinzufügen eines Dienstverweises** Dialogfeld in Visual Studio einen Verweis hinzufügen [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Dies erleichtert Ihnen den Zugriff auf einen Datendienst in einer Clientanwendung, den Sie in Visual Studio entwickeln. Wenn Sie diese Prozedur ausführen, werden Datenklassen auf Grundlage von aus dem Datendienst abgerufenen Metadaten generiert. Weitere Informationen finden Sie unter [Generieren der Datendienst-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).  
  
### <a name="to-add-a-data-service-reference"></a>So fügen Sie einen Datendienstverweis hinzu  
  
1.  (Optional) Wenn der Datendienst kein Teil der Projektmappe ist und nicht bereits ausgeführt ist, starten Sie den Datendienst und notieren Sie den URI des Datendiensts.  
  
2.  Mit der rechten Maustaste des Clientprojekts, und wählen Sie dann **Hinzufügen eines Dienstverweises**.  
  
3.  Wenn der Datendienst Teil der aktuellen Projektmappe ist, klicken Sie auf **Discover**.  
  
     - oder -   
  
     In der **Adresse** Textfeld die base-URL des Datendiensts, z. B. `http://localhost:1234/Northwind.svc`, und klicken Sie dann auf **Go**.  
  
4.  Klicken Sie auf **OK**.  
  
     Dadurch wird eine neue Codedatei hinzugefügt, die die zum Zugriff auf und zur Interaktion mit Datendienstressourcen als Objekte +verwendeten Datenklassen enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
