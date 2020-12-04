---
ms.openlocfilehash: 60e326af0d956ceb63b32e5d3ec2436fe09a7005
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "96592073"
---
Kopieren Sie die Dateien [mit einem SFTP-Client](https://www.raspberrypi.org/documentation/remote-access/ssh/sftp.md)aus dem Veröffentlichungsort auf dem Entwicklungs Computer in einen neuen Ordner auf dem Raspberry Pi.

Wenn Sie z. b. den `scp` Befehl verwenden möchten, um Dateien vom Entwicklungs Computer auf Ihren Raspberry Pi zu kopieren, öffnen Sie eine Eingabeaufforderung, und führen Sie den folgenden Befehl aus:

```console
scp -r /publish-location/* pi@raspberrypi:/home/pi/deployment-location/
```

Hierbei gilt Folgendes:

- Die- `-r` Option weist `scp` an, Dateien rekursiv zu kopieren.
- */Publish-Location/* ist der Ordner, den Sie im vorherigen Schritt veröffentlicht haben.
- `pi@raspberypi` der Benutzer-und der Hostname im Format `<username>@<hostname>` .
- */Home/Pi/Deployment-Location/* ist der neue Ordner auf dem Raspberry Pi.

> [!TIP]
> In den neueren Versionen von Windows ist OpenSSH enthalten, das `scp` bereits vorinstalliert ist.
