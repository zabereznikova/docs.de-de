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
ms.openlocfilehash: 0b95bab20299b966b9f3c6e6ce089a641670f974
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933414"
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a>Aspekte beim Hosten eines ActiveX-Steuerelements in Windows Forms
Obwohl Windows Forms zum Hosten von Windows Forms-Steuerelementen optimiert wurde, können Sie weiterhin ActiveX-Steuerelemente verwenden. Bei Verwendung von ActiveX-Steuerelementen in einer Anwendung sollten Sie Folgendes berücksichtigen:  
  
- **Sicherheit** Die Common Language Runtime wurde im Hinblick auf die Codezugriffssicherheit verbessert. Anwendungen mit Windows Forms können in einer voll vertrauenswürdigen Umgebung uneingeschränkt und in einer halb vertrauenswürdigen Umgebung mit Zugriff auf die meisten verfügbaren Funktionen ausgeführt werden. Windows Forms-Steuerelemente können problemlos in einem Browser integriert werden. Diese verbesserten Sicherheitsmerkmale können jedoch nicht genutzt werden, wenn ActiveX-Steuerelemente für Windows Forms verwendet werden. Das Ausführen eines ActiveX-Steuer Elements erfordert die nicht verwaltete Code-Berechtigung, <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> die mit der-Eigenschaft festgelegt wird. Weitere Informationen zur Sicherheit und zur Berechtigung für nicht verwalteten Code finden <xref:System.Security.Permissions.SecurityPermissionAttribute>Sie unter.  
  
- **Gesamtkosten** ActiveX-Steuerelemente, die einem Windows Form hinzugefügt werden, werden komplett mit diesem Windows Form weitergegeben. Dadurch können die erstellten Dateien unter Umständen sehr groß werden. Außerdem muss bei Verwendung von ActiveX-Steuerelementen für Windows Forms die Registrierung geändert werden. Damit wird stärker in den Computer des Benutzers eingegriffen als mit Windows Forms-Steuerelementen, bei denen dies nicht erforderlich ist.  
  
    > [!NOTE]
    > Zum Arbeiten mit ActiveX-Steuerelementen ist ein COM-Interop-Wrapper erforderlich. Weitere Informationen finden Sie unter [COM-Interoperabilität in Visual Basic und Visual C#](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
    > [!NOTE]
    > Wenn der Name eines Members des ActiveX-Steuer Elements mit einem Namen übereinstimmt, der in der .NET Framework definiert ist, wird das ActiveX-Steuerelement-Import Programm den Elementnamen <xref:System.Windows.Forms.AxHost> mit **CTL** versehen, wenn die abgeleitete Klasse erstellt wird. Wenn das ActiveX-Steuerelement z. b. über einen Member mit dem Namen **Layout**verfügt, wird es in der von AxHost abgeleiteten Klasse in **CtlLayout** umbenannt, da das **layoutereignis** innerhalb der .NET Framework definiert wird.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: ActiveX-Steuerelemente zu Windows Forms hinzufügen](how-to-add-activex-controls-to-windows-forms.md)
- [Codezugriffssicherheit](../../misc/code-access-security.md)
- [In zahlreichen Sprachen und Bibliotheken verglichene Steuerelemente und programmierbare Objekte](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Einfügen von Steuerelementen in Windows Forms](putting-controls-on-windows-forms.md)
- [Windows Forms-Steuerelemente](index.md)
