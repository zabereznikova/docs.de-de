---
title: 'Gewusst wie: Installieren und Deinstallieren von Diensten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, Windows Services
- installation, Windows Services
- uninstalling Windows Services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
caps.latest.revision: "19"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: bf767813f965b2c52a5061f74bbf2fab4572791b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-install-and-uninstall-services"></a>Gewusst wie: Installieren und Deinstallieren von Diensten
Wenn Sie einen Windows-Dienst mit dem.NET Framework entwickeln, können Sie die Dienstanwendung schnell installieren, indem Sie ein Befehlszeilen-Dienstprogramm InstallUtil.exe aufrufen. Wenn Sie ein Entwickler sind, der einen Windows-Dienst freigeben möchte, die Benutzer installieren und deinstallieren können, sollten Sie InstallShield verwenden. Finden Sie unter [Windows Installer-Bereitstellung](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
> [!WARNING]
>  Wenn Sie einen Dienst auf Ihrem Computer deinstallieren möchten, befolgen Sie die Schritte in diesem Artikel nicht. Stattdessen herauszufinden, welches Programm oder Software-Paket den Dienst installiert, und wählen Sie dann **Programme hinzufügen/entfernen** in der Systemsteuerung, um das Programm zu deinstallieren. Beachten Sie, dass viele Dienste Bestandteile von Windows sind; wenn Sie sie entfernen, können Sie die Instabilität des Systems verursachen.  
  
 Um die Schritte in diesem Artikel zu verwenden, müssen Sie zuerst einen Serviceinstaller auf dem Windows-Dienst hinzufügen. Finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung im Komponenten-Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
 Windows-Dienstprojekte können nicht durch Drücken von F5 direkt aus der Entwicklungsumgebung von Visual Studio ausgeführt werden. Der Grund besteht darin, dass die Dienste des Projekts installiert werden müssen, bevor das Projekt ausgeführt werden kann.  
  
> [!TIP]
>  Sie können starten **Server-Explorer** und stellen Sie sicher, dass der Dienst installiert oder deinstalliert wurde. Weitere Informationen finden Sie unter Vorgehensweise: Zugriff und Server-Explorer-Datenbank-Explorer zu initialisieren.  
  
### <a name="to-install-your-service-manually"></a>So installieren Sie einen Dienst manuell  
  
1.  Auf der Windows **starten** Menü oder **starten** Bildschirm **Visual Studio** , **Visual Studio-Tools**, **Developer Eingabeaufforderung**.  
  
     Eine Visual Studio-Eingabeaufforderung wird angezeigt.  
  
2.  Greifen Sie auf das Verzeichnis zu, in dem sich die kompilierte ausführbare Datei des Projekts befindet.  
  
3.  Führen Sie die Datei "InstallUtil.exe" von der Eingabeaufforderung aus. Übergeben Sie die Ausgabe des Projekts als Parameter.  
  
    ```  
    installutil <yourproject>.exe  
    ```  
  
     Wenn Sie die Visual Studio-Eingabeaufforderung verwenden, sollten InstallUtil.exe sich auf dem Systempfad befinden. Wenn dies nicht der Fall, können Sie den Pfad hinzufügen oder den vollständig qualifizierten Pfad verwenden, um es aufzurufen. Dieses Tool wird mit dem.NET Framework installiert und lautet `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`. Z. B. für die 32-Bit-Version von.NET Framework 4 oder 4.5. *, wenn Ihr Windows-Installationsverzeichnis C:\Windows, der Pfad ist `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`lautet. Für die 64-Bit-Version von .NET Framework 4 oder 4.5. \*, der Standardpfad lautet `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.  
  
### <a name="to-uninstall-your-service-manually"></a>So deinstallieren Sie einen Dienst manuell  
  
1.  Auf der Windows **starten** Menü oder **starten** Bildschirm **Visual Studio**, **Visual Studio-Tools**, **Developer Eingabeaufforderung**.  
  
     Eine Visual Studio-Eingabeaufforderung wird angezeigt.  
  
2.  Führen Sie die Datei "InstallUtil.exe" von der Eingabeaufforderung aus. Übergeben Sie die Ausgabe des Projekts als Parameter.  
  
    ```  
    installutil /u <yourproject>.exe  
    ```  
  
3.  In einigen Fällen könnte der Dienst noch in der Registrierung vorhanden sein, nachdem die ausführbaren Datei für einen Dienst gelöscht wurde. In diesem Fall verwenden Sie den Befehl [sc Delete](http://technet.microsoft.com/library/cc742045.aspx) aus der Registrierung den Eintrag für den Dienst zu entfernen.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Vorgehensweise: Erstellen von Windows-Diensten](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Installutil.exe (Installer-Tool)](../../../docs/framework/tools/installutil-exe-installer-tool.md)
