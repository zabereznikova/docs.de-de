---
title: FindPrivateKey-Beispiel – WCF
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: b89d135d7412f10cb9de1e4bda1aaab14b29cbf0
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490768"
---
# <a name="findprivatekey-sample"></a>FindPrivateKey-Beispiel

Es kann schwierig sein, den Speicherort und Namen der Privatschlüsseldatei zu finden, die einem bestimmten X.509-Zertifikat im Zertifikatspeicher zugeordnet ist. Das Tool FindPrivateKey.exe erleichtert diesen Prozess.

> [!IMPORTANT]
> FindPrivateKey ist ein Beispiel, das vor der Verwendung kompiliert werden muss. Finden Sie unter den [das FindPrivateKey-Projekt erstellen](#to-build-the-findprivatekey-project) Abschnitt die Anweisungen zum Erstellen des Tools findprivatekey bereit.

X.509-Zertifikate werden von einem Administrator oder einem beliebigen Benutzer auf dem Computer installiert. Allerdings kann das Zertifikat von einem Dienst unter einem anderen Konto zugegriffen werden. Z. B. das NETZWERKDIENST-Konto.

Dieses Konto verfügt möglicherweise nicht über Zugriff auf die Privatschlüsseldatei, da das Zertifikat nicht ursprünglich von diesem Konto installiert wurde. Das Tool FindPrivateKey gibt den Speicherort der Privatschlüsseldatei eines X.509-Zertifikats an. Sie können Berechtigungen in dieser Datei hinzufügen oder entfernen, wenn Sie den Speicherort der Privatschlüsseldatei der jeweiligen X.509-Zertifikate kennen.

Die Beispiele, die Zertifikate für die Sicherheit zu verwenden, verwenden das Tool FindPrivateKey in der *"Setup.bat"* Datei. Sobald eine Datei mit die private Schlüssel gefunden wurde, können Sie andere Tools wie z. B. *Cacls.exe* die richtigen Zugriffsrechte auf die Datei festlegen.

Stellen Sie sicher, dass das Benutzerkonto, das nur-Lese Zugriff auf die Datei hat, wenn ein Windows Communication Foundation (WCF)-Dienst unter einem Benutzerkonto, z. B. einen selbst gehosteten ausführbaren Datei, ausgeführt. Bei der Ausführung eines WCF-Diensts unter Internet Information Services (IIS) sind die Standardkonten, denen der Dienst ausgeführt, klicken Sie unter wird der Netzwerkdienst in IIS 7 und früheren Versionen oder Identität des Anwendungspools in IIS 7.5 und höhere Versionen. Weitere Informationen finden Sie unter [Anwendungspoolidentitäten](/iis/manage/configuring-security/application-pool-identities).

## <a name="examples"></a>Beispiele

Beim Zugriff auf ein Zertifikat für die der Prozess Leseberechtigung keine Ausnahmemeldung ähnlich wie im folgenden Beispiel angezeigt:

```
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

In diesem Fall verwenden Sie das FindPrivateKey-Tool, um eine Datei mit dem privaten Schlüssel zu suchen, und legen Sie dann die Zugriffsberechtigung für den Prozess, unter der Dienst ausgeführt wird. Beispielsweise kann dies mit dem Tool Cacls.exe erfolgen wie im folgenden Beispiel gezeigt:

```
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a>So erstellen Sie das FindPrivateKey-Projekt

Um das Projekt herunterzuladen, besuchen Sie [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).

1. Öffnen Sie den Datei-Explorer, und navigieren Sie zu der *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* Ordner, in dem Verzeichnis, in dem Sie das Beispiel installiert haben.

2. Doppelklicken Sie auf das Symbol für die SLN-Datei, um diese in Visual Studio zu öffnen.

3. In der **erstellen** , wählen Sie im Menü **Projektmappe neu erstellen**.

4. Erstellen der Projektmappe generiert die Datei: FindPrivateKey.exe.

## <a name="conventionscommand-line-entries"></a>Konventionen: befehlszeileneinträge

 "[*Option*]" stellt einen optionalen Satz von Parametern.

 "{*Option*}" stellt einen obligatorischen Satz von Parametern.

 "*option1* &#124; *option2*" eine Wahl zwischen Gruppen von Optionen darstellt.

 "\<*Wert*>" stellt einen Parameterwert eingegeben werden.

## <a name="usage"></a>Verwendung

```
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

Ort:

```
       <subjectName> The subject name of the certificate
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)
       -f            output file name only
       -d            output directory only
       -a            output absolute file name
```

Wenn keine Parameter an der Eingabeaufforderung angegeben werden, wird dann dieser Text angezeigt.

## <a name="examples"></a>Beispiele

In diesem Beispiel wird der Dateiname des Zertifikats mit dem Antragstellernamen "CN = Localhost", im persönlichen Speicher des aktuellen Benutzers.

```
FindPrivateKey My CurrentUser -n "CN=localhost"
```

In diesem Beispiel wird der Dateiname des Zertifikats mit dem Antragstellernamen "CN = Localhost" im persönlichen Speicher des aktuellen Benutzers und den vollständigen Verzeichnispfad ausgegeben.

```
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

In diesem Beispiel wird der Dateiname des Zertifikats mit dem Fingerabdruck "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" im persönlichen Speicher des lokalen Computers gesucht.

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
