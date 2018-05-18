---
title: 'Gewusst wie: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes'
description: Erfahren Sie, wie Sie die auf einem Computer installierten .NET Framework-Sicherheitsupdates und -Hotfixes ermitteln.
ms.date: 11/27/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6373def6859023377bf899f02d710c2ac6d83c44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a>Gewusst wie: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes

In diesem Artikel wird gezeigt, wie Sie die auf einem Computer installierten .NET Framework-Sicherheitsupdates und -Hotfixes ermitteln.

> [!NOTE]
> Alle in diesem Artikel gezeigten Techniken erfordern ein Konto mit Administratorberechtigungen.

## <a name="to-find-installed-updates-using-the-registry"></a>So ermitteln Sie mithilfe der Registrierung die installierten Updates

Die auf einem Computer installierten Sicherheitsupdates und Hotfixes für jede Version von .NET Framework werden in der Windows-Registrierung aufgeführt. Sie können diese Informationen mit dem Registrierungs-Editor (*regedit.exe*) anzeigen.

1. Öffnen Sie das Programm **regedit.exe**. Klicken Sie in Windows 8 und höheren Versionen mit der rechten Maustaste auf **Start** ![Windows-Lo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), und klicken Sie dann auf **Ausführen**. Geben Sie im Feld **Öffnen** den Namen **regedit.exe** ein, und klicken Sie auf **OK**.

2. Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     Die installierten Updates werden unter Unterschlüsseln aufgeführt, die die für sie geltende .NET Framework-Version identifizieren. Jedes Update wird durch eine Knowledge Base (KB)-Nummer identifiziert.

Im Registrierungs-Editor werden die .NET Framework-Versionen und die installierten Updates für jede Version in verschiedenen Unterschlüsseln gespeichert. Informationen zum Ermitteln der installierten Versionsnummern finden Sie unter [Gewusst wie: Bestimmen der installierten .NET Framework-Versionen](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a>So ermitteln Sie mithilfe einer Registrierungsabfrage im Code die installierten Updates

Im folgenden Beispiel werden die auf einem Computer installierten .NET Framework-Sicherheitsupdates und -Hotfixes programmgesteuert ermittelt:

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

Das Beispiel erzeugt eine Ausgabe, die der folgenden ähnelt:

```console
Microsoft .NET Framework 4 Client Profile
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
Microsoft .NET Framework 4 Extended
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
```

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a>So ermitteln Sie mithilfe einer Registrierungsabfrage in PowerShell die installierten Updates

Im folgenden Beispiel werden die auf einem Computer installierten .NET Framework-Sicherheitsupdates und -Hotfixes mithilfe von PowerShell ermittelt:

```powershell
$DotNetVersions = Get-ChildItem HKLM:\SOFTWARE\WOW6432Node\Microsoft\Updates | Where-Object {$_.name -like
 "*.NET Framework*"}

ForEach($Version in $DotNetVersions){
    
   $Updates = Get-ChildItem $Version.PSPath
    $Version.PSChildName
    ForEach ($Update in $Updates){
       $Update.PSChildName
       }
}
```

Das Beispiel erzeugt eine Ausgabe, die der folgenden ähnelt:

```console
Microsoft .NET Framework 4 Client Profile
KB2468871
KB2468871v2
KB2478063
KB2533523
KB2544514
KB2600211
KB2600217
Microsoft .NET Framework 4 Extended
KB2468871
KB2468871v2
KB2478063
KB2533523
KB2544514
KB2600211
KB2600217
```

## <a name="see-also"></a>Siehe auch

[Gewusst wie: Bestimmen der installierten .NET Framework-Versionen](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
[Installieren von.NET Framework für Entwickler](../../../docs/framework/install/guide-for-developers.md)  
[Versionen und Abhängigkeiten](../../../docs/framework/migration-guide/versions-and-dependencies.md)
