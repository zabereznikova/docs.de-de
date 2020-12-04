---
ms.openlocfilehash: 60e326af0d956ceb63b32e5d3ec2436fe09a7005
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "96592073"
---
<span data-ttu-id="70173-101">Kopieren Sie die Dateien [mit einem SFTP-Client](https://www.raspberrypi.org/documentation/remote-access/ssh/sftp.md)aus dem Veröffentlichungsort auf dem Entwicklungs Computer in einen neuen Ordner auf dem Raspberry Pi.</span><span class="sxs-lookup"><span data-stu-id="70173-101">[Using an SFTP client](https://www.raspberrypi.org/documentation/remote-access/ssh/sftp.md), copy the files from the publish location on the development computer to a new folder on the Raspberry Pi.</span></span>

<span data-ttu-id="70173-102">Wenn Sie z. b. den `scp` Befehl verwenden möchten, um Dateien vom Entwicklungs Computer auf Ihren Raspberry Pi zu kopieren, öffnen Sie eine Eingabeaufforderung, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="70173-102">For example, to use the `scp` command to copy files from the development computer to your Raspberry Pi, open a command prompt and execute the following:</span></span>

```console
scp -r /publish-location/* pi@raspberrypi:/home/pi/deployment-location/
```

<span data-ttu-id="70173-103">Hierbei gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="70173-103">Where:</span></span>

- <span data-ttu-id="70173-104">Die- `-r` Option weist `scp` an, Dateien rekursiv zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="70173-104">The `-r` option instructs `scp` to copy files recursively.</span></span>
- <span data-ttu-id="70173-105">*/Publish-Location/* ist der Ordner, den Sie im vorherigen Schritt veröffentlicht haben.</span><span class="sxs-lookup"><span data-stu-id="70173-105">*/publish-location/* is the folder you published to in the previous step.</span></span>
- <span data-ttu-id="70173-106">`pi@raspberypi` der Benutzer-und der Hostname im Format `<username>@<hostname>` .</span><span class="sxs-lookup"><span data-stu-id="70173-106">`pi@raspberypi` is the user and host names in the format `<username>@<hostname>`.</span></span>
- <span data-ttu-id="70173-107">*/Home/Pi/Deployment-Location/* ist der neue Ordner auf dem Raspberry Pi.</span><span class="sxs-lookup"><span data-stu-id="70173-107">*/home/pi/deployment-location/* is the new folder on the Raspberry Pi.</span></span>

> [!TIP]
> <span data-ttu-id="70173-108">In den neueren Versionen von Windows ist OpenSSH enthalten, das `scp` bereits vorinstalliert ist.</span><span class="sxs-lookup"><span data-stu-id="70173-108">Recent versions of Windows have OpenSSH, which includes `scp`, pre-installed.</span></span>
