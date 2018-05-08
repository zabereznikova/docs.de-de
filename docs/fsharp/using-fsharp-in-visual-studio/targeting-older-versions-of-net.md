---
title: .NET Framework 2.0 unter Windows 8
description: Erfahren Sie, ältere Version von .NET Framework abzielt, bei Verwendung von f#.
ms.date: 05/16/2016
ms.openlocfilehash: 9b08cced63b46778a5081d4de710991a6299fd29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="targeting-older-versions-of-net"></a>Für ältere Versionen von .NET

> [!NOTE]
Dieser Artikel ist nicht auf dem neuesten Stand mit den neuesten Visual Studio.  Es werden aktualisiert.

Der folgende Fehler kann auftreten, wenn Sie versuchen, die als Ziel .NET Framework 2.0, 3.0 oder 3.5 in f#-Projekt Wenn Visual Studio auf Windows 8.1 installiert ist: 

```
This project requires the 2.0 F# runtime, but that runtime is not installed.
```

Dieser Fehler ist bekannt unter die folgende Kombination von Bedingungen auftreten:


- Sie können Visual Studio auf Windows 8.1 installiert.
<br />

- .NET Framework 3.5 nicht aktiviert werden, vor der Installation von Visual Studio.
<br />

- Das Projekt auf .NET Framework 2.0, 3.0 oder 3.5 abzielt.
<br />

Bei der Installation von Visual Studio erkennt die installierten Versionen von .NET Framework und installiert die f# Runtime 2.0 nur, wenn .NET Framework 3.5 installiert und aktiviert ist.


## <a name="resolving-the-error"></a>Beim Beheben des Fehlers
Um diesen Fehler zu beheben, können Sie entweder eine neuere Version von .NET Framework-Ziel oder können Sie Aktivieren von .NET Framework 3.5 auf Windows 8.1 und installieren Sie dann auf die Laufzeit f# 2.0 durch Ausführen des Setupprogramms für Visual Studio mit der **Reparatur** -Option.


#### <a name="to-enable-the-net-framework-35-on-windows-81"></a>So aktivieren Sie .NET Framework 3.5 auf Windows 8.1

1. Auf der **starten** Bildschirm, eingeben starten **Systemsteuerung**.
<br />  Wie Sie diesen Namen, geben Sie die **Systemsteuerung** Symbol angezeigt wird, unter der **Apps** Überschrift.
<br />

2. Wählen Sie die **Systemsteuerung** Symbol, wählen Sie die **Programme** Symbol, und wählen Sie dann die **Windows-Funktionen ein- oder ausschalten** Link.
<br />

3. Stellen Sie sicher, dass die **.NET Framework 3.5 (umfasst .NET 2.0 und 3.0)** Kontrollkästchen ausgewählt ist, und wählen Sie dann die **OK** Schaltfläche.
<br />  Sie müssen das Kontrollkästchen für alle untergeordneten Knoten für die optionalen Komponenten von .NET Framework.
<br />  .NET Framework 3.5 ist aktiviert, wenn dies noch nicht geschehen.
<br />


#### <a name="to-install-the-f-20-runtime"></a>So installieren Sie die Laufzeit 2.0 [F#]

1. Wählen Sie in der Systemsteuerung die **Programme** verknüpfen, und wählen Sie dann die **Programme und Funktionen** Link.
<br />

2. Wählen Sie in der Liste der installierten Programme, die Edition von Visual Studio, die Sie installiert, und wählen Sie dann die **Änderung** Schaltfläche.
<br />

3. Nach dem Setup gestartet wird, wählen Sie die **Reparatur** Schaltfläche.
<br />  Weitere Informationen finden Sie unter [Installieren von Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).
<br />
## <a name="see-also"></a>Siehe auch
[Visual F#](../index.md)
