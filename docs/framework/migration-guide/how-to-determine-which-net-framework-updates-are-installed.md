---
title: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes
description: Erfahren Sie, wie Sie die auf einem Computer installierten .NET Framework-Sicherheitsupdates und -Hotfixes ermitteln.
ms.date: 11/27/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
ms.openlocfilehash: 5c7bf48d5786530a9bcb69fb7cf605ac2c80a4eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181269"
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a>Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes

In diesem Artikel wird gezeigt, wie Sie die auf einem Computer installierten .NET Framework-Sicherheitsupdates und -Hotfixes ermitteln.

> [!NOTE]
> Alle in diesem Artikel gezeigten Techniken erfordern ein Konto mit Administratorberechtigungen.

## <a name="use-registry-editor"></a>Verwenden des Registrierungs-Editors

Die auf einem Computer installierten Sicherheitsupdates und Hotfixes für jede Version von .NET Framework werden in der Windows-Registrierung aufgeführt. Sie können diese Informationen mit dem Registrierungs-Editor (*regedit.exe*) anzeigen.

1. Öffnen Sie das Programm **regedit.exe**. Klicken Sie in Windows 8 und höheren Versionen mit der rechten Maustaste auf **Start** ![Screenshot des Logos der WINDOWS-TASTE.](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo"), und klicken Sie dann auf **Ausführen**. Geben Sie im Feld **Öffnen** den Namen **regedit.exe** ein, und klicken Sie auf **OK**.

2. Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel:

     **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates**

     Die installierten Updates werden unter Unterschlüsseln aufgeführt, die die für sie geltende .NET Framework-Version identifizieren. Jedes Update wird durch eine Knowledge Base (KB)-Nummer identifiziert.

Im Registrierungs-Editor werden die .NET Framework-Versionen und die installierten Updates für jede Version in verschiedenen Unterschlüsseln gespeichert. Informationen zum Ermitteln der installierten Versionsnummern finden Sie unter [Gewusst wie: Bestimmen der installierten .NET Framework-Versionen](how-to-determine-which-versions-are-installed.md).

## <a name="query-the-registry-using-code"></a>Abfragen der Registrierung mithilfe von Code

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

## <a name="use-powershell-to-query-the-registry"></a>Abfragen der Registrierung mithilfe von PowerShell

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

## <a name="see-also"></a>Weitere Informationen

- [Gewusst wie: Bestimmen der installierten .NET Framework-Versionen](how-to-determine-which-versions-are-installed.md)
- [Installieren von.NET Framework für Entwickler](../install/guide-for-developers.md)
- [Versionen und Abhängigkeiten](versions-and-dependencies.md)
