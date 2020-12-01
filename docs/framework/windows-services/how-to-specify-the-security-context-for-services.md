---
title: 'Vorgehensweise: Angeben des Sicherheitskontexts für Dienste'
description: Geben Sie den Sicherheitskontext für Dienste an. Dienste, die im Kontext des Standardsystemkontos ausgeführt werden, haben andere Zugriffsrechte für Systemressourcen als der angemeldete Benutzer.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
ms.openlocfilehash: dcf0680f1bcb0f0e927bdb37ea56f7b3025be09b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270536"
---
# <a name="how-to-specify-the-security-context-for-services"></a>Vorgehensweise: Angeben des Sicherheitskontexts für Dienste

Standardmäßig werden Dienste in einem anderen Sicherheitskontext ausgeführt als dem des angemeldeten Benutzers. Dienste werden im Kontext des Standardsystemkontos, `LocalSystem`, ausgeführt, das ihnen andere Zugriffsberechtigungen für Systemressourcen erteilt als dem Benutzer. Sie können dieses Verhalten ändern und ein anderes Benutzerkonto angeben, unter dem Ihr Dienst ausgeführt werden sollte.  
  
 Der Sicherheitskontext lässt sich festlegen, indem Sie die Eigenschaft <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> für den Prozess bearbeiten, in dem der Dienst ausgeführt wird. Mit dieser Eigenschaft können Sie den Dienst auf einen von vier Kontotypen festlegen:  
  
- `User`: Bewirkt, dass das System bei der Installation des Diensts zur Eingabe eines gültigen Benutzernamens und eines gültigen Kennworts auffordert und im Zusammenhang mit einem Konto ausgeführt wird, das von einem Benutzer im Netzwerk angegeben wurde.  
  
- `LocalService`: Wird im Zusammenhang mit einem Konto ausgeführt, das als nicht berechtigter Benutzer des lokalen Computers fungiert, und stellt für beliebige Remoteserver Anmeldeinformationen bereit.  
  
- `LocalSystem`: Wird im Zusammenhang mit einem Konto ausgeführt, auf dem umfassende lokale Berechtigungen bereitgestellt werden, und stellt für beliebige Remoteserver die Anmeldeinformationen des Computers bereit.  
  
- `NetworkService`: Wird im Zusammenhang mit einem Konto ausgeführt, das als nicht berechtigter Benutzer des lokalen Computers fungiert, und stellt für beliebige Remoteserver die Anmeldeinformationen des Computers bereit.  
  
 Weitere Informationen finden Sie unter der <xref:System.ServiceProcess.ServiceAccount>-Enumeration.  
  
### <a name="to-specify-the-security-context-for-a-service"></a>Angeben des Sicherheitskontexts für einen Dienst  
  
1. Nachdem Sie den Dienst erstellt haben, fügen Sie die erforderlichen Installationsprogramme hinzu. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](how-to-add-installers-to-your-service-application.md).  
  
2. Greifen Sie im Designer auf die Klasse `ProjectInstaller` zu, und klicken Sie bei dem Prozess, mit dem Sie arbeiten, auf den Dienstprozessinstaller.  
  
    > [!NOTE]
    > Die Klasse `ProjectInstaller` enthält für jede Dienstanwendung mindestens zwei Installationskomponenten: eine Komponente, welche die Prozesse für sämtliche Dienste im Projekt installiert, und einen Installer für jeden in der App enthaltenen Dienst. Wählen Sie in dieser Instanz <xref:System.ServiceProcess.ServiceProcessInstaller> aus.  
  
3. Legen Sie im Fenster **Eigenschaften**<xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> auf den entsprechenden Wert fest.  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in Windows-Dienstanwendungen](introduction-to-windows-service-applications.md)
- [How to: Hinzufügen von Installern zur Dienstanwendung](how-to-add-installers-to-your-service-application.md)
- [How to: Erstellen von Windows-Diensten](how-to-create-windows-services.md)
