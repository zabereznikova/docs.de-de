---
title: Überlegungen zum Integrieren eines ActiveX-Steuerelements in ein Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
ms.openlocfilehash: 52977ea11745056f7e022d545705d989d2e1bbc8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a>Überlegungen zum Integrieren eines ActiveX-Steuerelements in ein Windows Form
Obwohl Windows Forms zum Hosten von Windows Forms-Steuerelementen optimiert wurde, können Sie weiterhin ActiveX-Steuerelemente verwenden. Bei Verwendung von ActiveX-Steuerelementen in einer Anwendung sollten Sie Folgendes berücksichtigen:  
  
-   **Sicherheit** Die Common Language Runtime wurde im Hinblick auf die Codezugriffssicherheit verbessert. Anwendungen mit Windows Forms können in einer voll vertrauenswürdigen Umgebung uneingeschränkt und in einer halb vertrauenswürdigen Umgebung mit Zugriff auf die meisten verfügbaren Funktionen ausgeführt werden. Windows Forms-Steuerelemente können problemlos in einem Browser integriert werden. Diese verbesserten Sicherheitsmerkmale können jedoch nicht genutzt werden, wenn ActiveX-Steuerelemente für Windows Forms verwendet werden. Ausführen eines ActiveX-Steuerelements erfordert die Berechtigung für nicht verwalteten Code, mit festgelegt ist die <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> Eigenschaft. Weitere Informationen zu Sicherheit und die Berechtigung von nicht verwaltetem Code finden Sie unter <xref:System.Security.Permissions.SecurityPermissionAttribute>.  
  
-   **Gesamtkosten** ActiveX-Steuerelemente, die einem Windows Form hinzugefügt werden, werden komplett mit diesem Windows Form weitergegeben. Dadurch können die erstellten Dateien unter Umständen sehr groß werden. Außerdem muss bei Verwendung von ActiveX-Steuerelementen für Windows Forms die Registrierung geändert werden. Damit wird stärker in den Computer des Benutzers eingegriffen als mit Windows Forms-Steuerelementen, bei denen dies nicht erforderlich ist.  
  
    > [!NOTE]
    >  Zum Arbeiten mit ActiveX-Steuerelementen ist ein COM-Interop-Wrapper erforderlich. Weitere Informationen finden Sie unter [COM-Interoperabilität in Visual Basic und Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
    > [!NOTE]
    >  Wenn der Name eines Members des ActiveX-Steuerelements einen im definierten Namen übereinstimmt, die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], der ActiveX Control Importer den Membernamen das Präfix wird **Ctl** beim Erstellen der <xref:System.Windows.Forms.AxHost> abgeleitete Klasse. Wenn beispielsweise das ActiveX-Steuerelement ein Member mit dem Namen **Layout** enthält, wird dieser Name in der von AxHost abgeleiteten Klasse in **CtlLayout** geändert, da in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] das **Layout**-Ereignis bereits definiert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Hinzufügen von ActiveX-Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [Codezugriffssicherheit](../../../../docs/framework/misc/code-access-security.md)  
 [In zahlreichen Sprachen und Bibliotheken verglichene Steuerelemente und programmierbare Objekte](http://msdn.microsoft.com/library/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [Einfügen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)
