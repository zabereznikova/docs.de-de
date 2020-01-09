---
title: FindPrivateKey-Beispiel
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: 0ed1e5e81a5d2f7f3586e5dce306e8244b5ebd48
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346019"
---
# <a name="findprivatekey-sample"></a>FindPrivateKey-Beispiel

Es kann schwierig sein, den Speicherort und Namen der Privatschlüsseldatei zu finden, die einem bestimmten X.509-Zertifikat im Zertifikatspeicher zugeordnet ist. Das Tool FindPrivateKey.exe erleichtert diesen Prozess.

> [!IMPORTANT]
> FindPrivateKey ist ein Beispiel, das vor der Verwendung kompiliert werden muss. Anweisungen zum Erstellen des Tools FindPrivateKey finden Sie im Abschnitt so [Erstellen Sie das FindPrivateKey-Projekt](#to-build-the-findprivatekey-project) .

X.509-Zertifikate werden von einem Administrator oder einem beliebigen Benutzer auf dem Computer installiert. Auf das Zertifikat kann jedoch von einem Dienst zugegriffen werden, der unter einem anderen Konto ausgeführt wird. Beispielsweise das Netzwerkdienst Konto.

Dieses Konto verfügt möglicherweise nicht über Zugriff auf die Privatschlüsseldatei, da das Zertifikat nicht ursprünglich von diesem Konto installiert wurde. Das Tool FindPrivateKey gibt den Speicherort der Privatschlüsseldatei eines X.509-Zertifikats an. Sie können Berechtigungen in dieser Datei hinzufügen oder entfernen, wenn Sie den Speicherort der Privatschlüsseldatei der jeweiligen X.509-Zertifikate kennen.

In den Beispielen für die Verwendung von Zertifikaten für die Sicherheit wird das Tool FindPrivateKey in der Datei *Setup. bat* verwendet. Nachdem die Datei mit dem privaten Schlüssel gefunden wurde, können Sie andere Tools, wie z. b *. cacls. exe* , verwenden, um die entsprechenden Zugriffsrechte auf die Datei festzulegen.

Wenn Sie einen Windows Communication Foundation (WCF)-Dienst unter einem Benutzerkonto ausführen (z. b. eine selbstgeh ostete ausführbare Datei), stellen Sie sicher, dass das Benutzerkonto schreibgeschützten Zugriff auf die Datei hat. Beim Ausführen eines WCF-Dienstanbieter unter Internetinformationsdienste (IIS) werden die Standardkonten, unter denen der-Dienst ausgeführt wird, der Netzwerkdienst in IIS 7 und früheren Versionen oder die Anwendungs Pool Identität auf IIS 7,5 und höheren Versionen. Weitere Informationen finden Sie unter [Anwendungs Pool Identitäten](/iis/manage/configuring-security/application-pool-identities).

## <a name="examples"></a>Beispiele

Wenn Sie auf ein Zertifikat zugreifen, für das der Prozess nicht über Leseberechtigungen verfügt, wird eine Ausnahme Meldung wie im folgenden Beispiel angezeigt:

```output
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

Verwenden Sie in diesem Fall das Tool FindPrivateKey, um die Datei mit dem privaten Schlüssel zu suchen, und legen Sie dann das Zugriffsrecht für den Prozess fest, unter dem der Dienst ausgeführt wird. Dies kann z. b. mit dem Tool cacls. exe erfolgen, wie im folgenden Beispiel gezeigt:

```console
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a>So erstellen Sie das FindPrivateKey-Projekt

Um das Projekt herunterzuladen, besuchen Sie [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).

1. Öffnen Sie den Datei-Explorer, und navigieren Sie zum Ordner *WF_WCF_Samples \wcf\setup\findprivatekey\cs* unter dem Verzeichnis Speicherort, in dem Sie das Beispiel installiert haben.

2. Doppelklicken Sie auf das Symbol für die SLN-Datei, um diese in Visual Studio zu öffnen.

3. Wählen Sie im Menü **Erstellen** die Option Projekt Mappe **neu erstellen**aus.

4. Beim Erstellen der Projektmappe wird die Datei "FindPrivateKey.exe" erstellt.

## <a name="conventionscommand-line-entries"></a>Konventionen – Befehlszeilen Einträge

 "[*Option*]" stellt einen optionalen Satz von Parametern dar.

 "{*Option*}" stellt einen obligatorischen Satz von Parametern dar.

 "*Option1* &#124; *Option2*" stellt eine Auswahl zwischen Options Sätzen dar.

 "\<*Wert*>" stellt einen Parameterwert dar, der eingegeben werden soll.

## <a name="usage"></a>Verwendungs-

```console
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

Dabei gilt Folgendes:

| Parameter         | Beschreibung                                                                       |
|-----------------|-----------------------------------------------------------------------------------|
| `<subjectName>` | Der Antragsteller Name des Zertifikats.                                               |
| `<thumbprint>`  | Der Fingerabdruck des Zertifikats (Sie können das Tool "Certmgr. exe" verwenden, um dies zu finden) |
| `-f`            | nur Ausgabe Dateiname                                                             |
| `-d`            | nur Ausgabeverzeichnis                                                             |
| `-a`            | absoluten Dateinamen ausgeben                                                         |

Wenn keine Parameter an der Eingabeaufforderung angegeben werden, wird der Hilfetext mit diesen Informationen angezeigt.

## <a name="examples"></a>Beispiele

In diesem Beispiel wird der Dateiname des Zertifikats mit dem Antragsteller Namen "CN = localhost" im persönlichen Speicher des aktuellen Benutzers ermittelt.

```console
FindPrivateKey My CurrentUser -n "CN=localhost"
```

In diesem Beispiel wird der Dateiname des Zertifikats mit dem Antragsteller Namen "CN = localhost" im persönlichen Speicher des aktuellen Benutzers gesucht und der vollständige Verzeichnispfad ausgegeben.

```console
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

In diesem Beispiel wird der Dateiname des Zertifikats mit dem Fingerabdruck "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" im persönlichen Speicher des lokalen Computers gesucht.

```console
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
