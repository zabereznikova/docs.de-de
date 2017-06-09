---
title: "How to: Specify the Security Context for Services | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Windows Service applications, security"
  - "security [Visual Studio], contexts"
  - "contexts, Visual Studio security"
  - "security [Visual Studio], service applications"
  - "ServiceProcessInstaller class, security context"
  - "services, security"
  - "ServiceInstaller class, security context"
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 10
---
# How to: Specify the Security Context for Services
Standardmäßig können Dienste in einem anderen Sicherheitskontext als dem von angemeldeten Benutzern ausgeführt werden.  Dienste werden im Kontext des `LocalSystem` genannten Standardsystemkontos ausgeführt. Sie erhalten dadurch andere Zugriffsberechtigungen auf Systemressourcen als der Benutzer.  Dieses Verhalten kann geändert und ein anderes Benutzerkonto angegeben werden, unter dem der Dienst ausgeführt werden soll.  
  
 Der Sicherheitskontext kann durch Ändern der <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A>\-Eigenschaft für den Prozess festgelegt werden, in dem der Dienst ausgeführt wird.  Über diese Eigenschaft können Sie den Dienst auf einen der folgenden vier Kontotypen festlegen:  
  
-   `User`: Das System fordert zur Eingabe eines gültigen Benutzernamens und Kennworts auf, wenn der Dienst installiert wird und im Kontext eines von einem einzelnen Benutzer im Netzwerk angegebenen Kontos ausgeführt wird.  
  
-   `LocalService`: Die Ausführung erfolgt im Kontext eines Kontos, das auf dem lokalen Computer als Benutzer ohne Berechtigungen fungiert. Remoteservern werden anonyme Anmeldeinformationen übergeben.  
  
-   `LocalSystem`, das im Kontext eines Kontos ausgeführt, das umfangreiche lokale Berechtigungen bereitgestellt werden, und stellt die Anmeldeinformationen des Computers jedem Remoteserver dar;  
  
-   `NetworkService`: Die Ausführung erfolgt im Kontext eines Kontos, das auf dem lokalen Computer als Benutzer ohne Berechtigungen fungiert. Remoteservern werden die Anmeldeinformationen des Computers übergeben.  
  
 Weitere Informationen finden Sie unter der <xref:System.ServiceProcess.ServiceAccount>\-Enumeration.  
  
### So geben Sie den Sicherheitskontext für einen Dienst an  
  
1.  Nachdem Sie den Dienst erstellt haben, fügen Sie die erforderlichen Installationsprogramme hinzu.  Weitere Informationen finden Sie unter [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
2.  Greifen Sie im Designer auf die `ProjectInstaller`\-Klasse zu, und klicken Sie auf das Dienstprozess\-Installationsprogramm für den Dienst, mit dem Sie arbeiten.  
  
    > [!NOTE]
    >  Für jede Dienstanwendung sind mindestens zwei Installationskomponenten in der `ProjectInstaller`\-Klasse enthalten: eine Komponente, von der die Prozesse für alle Dienste im Projekt installiert werden, und ein Installationsprogramm für jeden Dienst, der in der Anwendung enthalten ist.  In diesem Beispiel wird <xref:System.ServiceProcess.ServiceProcessInstaller> ausgewählt.  
  
3.  Legen Sie den <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> im **Eigenschaftenfenster** auf den entsprechenden Wert fest.  
  
## Siehe auch  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)   
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)