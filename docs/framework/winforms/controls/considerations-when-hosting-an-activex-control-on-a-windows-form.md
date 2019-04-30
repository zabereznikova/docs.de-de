---
title: Aspekte beim Hosten eines ActiveX-Steuerelements in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
ms.openlocfilehash: babae31a3be9775d07ca84c54e1177d297cab5cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956272"
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a>Aspekte beim Hosten eines ActiveX-Steuerelements in Windows Forms
Obwohl Windows Forms zum Hosten von Windows Forms-Steuerelementen optimiert wurde, können Sie weiterhin ActiveX-Steuerelemente verwenden. Bei Verwendung von ActiveX-Steuerelementen in einer Anwendung sollten Sie Folgendes berücksichtigen:  
  
- **Sicherheit** Die Common Language Runtime wurde im Hinblick auf die Codezugriffssicherheit verbessert. Anwendungen mit Windows Forms können in einer voll vertrauenswürdigen Umgebung uneingeschränkt und in einer halb vertrauenswürdigen Umgebung mit Zugriff auf die meisten verfügbaren Funktionen ausgeführt werden. Windows Forms-Steuerelemente können problemlos in einem Browser integriert werden. Diese verbesserten Sicherheitsmerkmale können jedoch nicht genutzt werden, wenn ActiveX-Steuerelemente für Windows Forms verwendet werden. Ausführen eines ActiveX-Steuerelements erfordert eine Berechtigung nicht verwaltetem Code mit festgelegt ist die <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> Eigenschaft. Weitere Informationen zu Sicherheit und die Berechtigung für nicht verwalteten Code, finden Sie unter <xref:System.Security.Permissions.SecurityPermissionAttribute>.  
  
- **Gesamtkosten** ActiveX-Steuerelemente, die einem Windows Form hinzugefügt werden, werden komplett mit diesem Windows Form weitergegeben. Dadurch können die erstellten Dateien unter Umständen sehr groß werden. Außerdem muss bei Verwendung von ActiveX-Steuerelementen für Windows Forms die Registrierung geändert werden. Damit wird stärker in den Computer des Benutzers eingegriffen als mit Windows Forms-Steuerelementen, bei denen dies nicht erforderlich ist.  
  
    > [!NOTE]
    >  Zum Arbeiten mit ActiveX-Steuerelementen ist ein COM-Interop-Wrapper erforderlich. Weitere Informationen finden Sie unter [COM-Interoperabilität in Visual Basic und Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
    > [!NOTE]
    >  Wenn der Name eines Members des ActiveX-Steuerelements mit einem Namen, die in definierten übereinstimmt der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], und klicken Sie dann der ActiveX Control Importer den Membernamen mit dem Präfix **Ctl** beim Erstellen der <xref:System.Windows.Forms.AxHost> abgeleitete Klasse. Wenn beispielsweise das ActiveX-Steuerelement ein Member mit dem Namen **Layout** enthält, wird dieser Name in der von AxHost abgeleiteten Klasse in **CtlLayout** geändert, da in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] das **Layout**-Ereignis bereits definiert ist.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Hinzufügen von ActiveX-Steuerelemente zu Windows Forms](how-to-add-activex-controls-to-windows-forms.md)
- [Codezugriffssicherheit](../../misc/code-access-security.md)
- [In zahlreichen Sprachen und Bibliotheken verglichene Steuerelemente und programmierbare Objekte](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Einfügen von Steuerelementen in Windows Forms](putting-controls-on-windows-forms.md)
- [Windows Forms-Steuerelemente](index.md)
