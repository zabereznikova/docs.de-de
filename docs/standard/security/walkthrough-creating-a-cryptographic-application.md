---
title: 'Exemplarische Vorgehensweise: Erstellen einer kryptografischen Anwendung'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [NET Framework], example
- cryptography [NET Framework], cryptographic application example
- cryptography [NET Framework], application example
ms.assetid: abf48c11-1e72-431d-9562-39cf23e1a8ff
ms.openlocfilehash: 246028566c59e5c8a77b26a21729d3f143d38d07
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289706"
---
# <a name="walkthrough-creating-a-cryptographic-application"></a>Exemplarische Vorgehensweise: Erstellen einer kryptografischen Anwendung
Diese exemplarische Vorgehensweise veranschaulicht, wie Inhalt verschlüsselt und entschlüsselt wird. Die Codebeispiele sind für eine Windows Forms-Anwendung vorgesehen. Diese Anwendung zeigt keine realen Szenarien wie die Verwendung von Smartcards. Stattdessen veranschaulicht sie die Grundlagen der Ver- und Entschlüsselung.  
  
 In dieser exemplarische Vorgehensweise werden die folgenden Richtlinien für Verschlüsselung verwendet:  
  
- Verwenden Sie die <xref:System.Security.Cryptography.RijndaelManaged>-Klasse (ein symmetrischer Algorithmus), um Daten zu ver- und entschlüsseln, indem Sie den automatisch generierten Schlüssel (<xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A>) und Initialisierungsvektor (<xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>) verwenden.  
  
- Verwenden Sie den <xref:System.Security.Cryptography.RSACryptoServiceProvider> (ein asymmetrischer Algorithmus), um den Schlüssel für die Daten zu ver- und zu entschlüsseln, die mit <xref:System.Security.Cryptography.RijndaelManaged> verschlüsselt wurden. Asymmetrische Algorithmen sind am besten für kleinere Datenmengen geeignet, zum Beispiel für einen Schlüssel.  
  
    > [!NOTE]
    > Wenn Sie Daten auf Ihrem Computer schützen möchten, anstatt verschlüsselte Inhalte mit anderen Personen auszutauschen, sollten Sie überlegen, die <xref:System.Security.Cryptography.ProtectedData>-Klasse oder die <xref:System.Security.Cryptography.ProtectedMemory>-Klasse zu verwenden.  
  
 In der folgenden Tabelle sind die kryptografischen Aufgaben in diesem Thema zusammengefasst.  
  
|Aufgabe|BESCHREIBUNG|  
|----------|-----------------|  
|Erstellen einer Windows Forms-Anwendung|Listet die Steuerelemente auf, die zum Ausführen der Anwendung erforderlich sind.|  
|Deklarieren von globalen Objekten|Deklariert Zeichenfolgenpfadvariablen, die <xref:System.Security.Cryptography.CspParameters> und den <xref:System.Security.Cryptography.RSACryptoServiceProvider>, um den globalen Kontext der <xref:System.Windows.Forms.Form>-Klasse zu erhalten.|  
|Erstellen eines asymmetrischen Schlüssels|Erstellt ein asymmetrisches öffentliches und privates Schlüsselwertpaar und weist ihm einen Schlüsselcontainernamen zu.|  
|Verschlüsseln einer Datei|Zeigt ein Dialogfeld an, in dem eine Datei für die Verschlüsselung ausgewählt wird, und verschlüsselt die Datei.|  
|Entschlüsseln einer Datei|Zeigt ein Dialogfeld an, in dem eine verschlüsselte Datei für die Entschlüsselung ausgewählt wird, und entschlüsselt die Datei.|  
|Abrufen eines privaten Schlüssels|Ruft das volle Schlüsselpaar über den Schlüsselcontainernamen ab.|  
|Exportieren eines öffentlichen Schlüssels|Speichert den Schlüssel in einer XML-Datei mit ausschließlich öffentlichen Parametern.|  
|Importieren eines öffentlichen Schlüssels|Lädt den Schlüssel aus einer XML-Datei in den Schlüsselcontainer.|  
|Testen der Anwendung|Listet Verfahren zum Testen dieser Anwendung auf.|  
  
## <a name="prerequisites"></a>Voraussetzungen  
 Zum Abschließen dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
- Verweise auf die Namespaces <xref:System.IO> und <xref:System.Security.Cryptography>.  
  
## <a name="creating-a-windows-forms-application"></a>Erstellen einer Windows Forms-Anwendung  
 Die meisten Codebeispiele in dieser exemplarischen Vorgehensweise sind als Ereignishandler für Button-Steuerelemente konzipiert. In der folgenden Tabelle sind die Steuerelemente aufgelistet, die für die Beispielanwendung und die erforderlichen Namen benötigt werden, um mit den Codebeispielen übereinzustimmen.  
  
|Control|Name|Texteigenschaft (nach Bedarf)|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|Datei verschlüsseln|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|Datei entschlüsseln|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|Schlüssel erstellen|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|Öffentlichen Schlüssel exportieren|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|Öffentlichen Schlüssel importieren|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|Privaten Schlüssel abrufen|  
|<xref:System.Windows.Forms.Label>|`label1`|Schlüssel nicht festgelegt|  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 Doppelklicken Sie auf die Schaltflächen im Visual Studio-Designer, um deren Ereignishandler zu erstellen.  
  
## <a name="declaring-global-objects"></a>Deklarieren von globalen Objekten  
 Fügen Sie dem Konstruktor des Form-Objekts folgenden Code hinzu. Bearbeiten Sie die Zeichenfolgenvariablen für Ihre Umgebung und Einstellungen.  
  
 [!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
 [!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a>Erstellen eines asymmetrischen Schlüssels  
 Mit dieser Aufgabe wird ein asymmetrischer Schlüssel erstellt, der den <xref:System.Security.Cryptography.RijndaelManaged>-Schlüssel ver- und entschlüsselt. Dieser Schlüssel wurde verwendet, um den Inhalt zu verschlüsseln, und zeigt den Schlüsselcontainernamen auf dem Label-Steuerelement an.  
  
 Fügen Sie folgenden Code als `Click`-Ereignishandler für die `Create Keys`-Schaltfläche hinzu (`buttonCreateAsmKeys_Click`).  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a>Verschlüsseln einer Datei  
 Diese Aufgabe umfasst zwei Methoden: die Ereignishandlermethode für die `Encrypt File` Schaltfläche ( `buttonEncryptFile_Click` ) und die- `EncryptFile` Methode. Die erste Methode zeigt ein Dialogfeld zum Auswählen einer Datei an und übergibt den Dateinamen an die zweite Methode, die die Verschlüsselung ausführt.  
  
 Der verschlüsselte Inhalt, der Schlüssel und der IV werden zusammen in einem <xref:System.IO.FileStream>-Objekt gespeichert, das als Verschlüsselungspaket bezeichnet wird.  
  
 Die `EncryptFile`-Methode führt folgende Schritte aus:  
  
1. Sie erstellt einen symmetrischen <xref:System.Security.Cryptography.RijndaelManaged>-Algorithmus, um den Inhalt zu verschlüsseln.  
  
2. Sie erstellt ein <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Objekt, um den <xref:System.Security.Cryptography.RijndaelManaged>-Schlüssel zu verschlüsseln.   
  
3. Sie verwendet ein <xref:System.Security.Cryptography.CryptoStream>-Objekt, um den <xref:System.IO.FileStream> der Quelldatei in Byteblöcken in ein Ziel-<xref:System.IO.FileStream>-Objekt für die verschlüsselte Datei zu lesen und zu verschlüsseln.  
  
4. Sie ermittelt die Länge des verschlüsselten Schlüssels und IVs und erstellt Bytearrays mit deren Längenwerten.  
  
5. Sie schreibt den Schlüssel, den IV und deren Längenwerte in das verschlüsselte Paket.  
  
 Das Verschlüsselungspaket hat das folgende Format:  
  
- Schlüssellänge, Bytes 0 - 3  
  
- IV-Länge, Bytes 4 - 7  
  
- Verschlüsselte Schlüssel  
  
- IV  
  
- Verschlüsselungsverfahrenstext  
  
 Durch die Längenangaben für den Schlüssel und den IV lassen sich Startpunkte und Längen aller Teile des Verschlüsselungspakets bestimmen. Diese können dann zum Entschlüsseln der Datei verwendet werden.  
  
 Fügen Sie folgenden Code als `Click`-Ereignishandler für die `Encrypt File`-Schaltfläche hinzu (`buttonEncryptFile_Click`).  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 Fügen Sie dem Form-Objekt die folgende `EncryptFile`-Methode hinzu.  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a>Entschlüsseln einer Datei  
 Diese Aufgabe bedingt zwei Methoden: die Ereignishandlermethode für die `Decrypt File`-Schaltfläche (`buttonDecryptFile_Click`) und die `DecryptFile`-Methode. Die erste Methode zeigt ein Dialogfeld zum Auswählen einer Datei an und übergibt den Dateinamen an die zweite Methode, die die Entschlüsselung ausführt.  
  
 Die `Decrypt`-Methode führt folgende Schritte aus:  
  
1. Sie erstellt einen symmetrischen <xref:System.Security.Cryptography.RijndaelManaged>-Algorithmus, um den Inhalt zu entschlüsseln.  
  
2. Sie liest die ersten acht Bytes des <xref:System.IO.FileStream>-Objekts des verschlüsselten Pakets in Bytearrays ein, um die Länge des verschlüsselten Schlüssels und IVs zu erhalten.  
  
3. Sie extrahiert den Schlüssel und den IV aus dem Verschlüsselungspaket in Bytearrays hinein.  
  
4. Sie erstellt ein <xref:System.Security.Cryptography.RSACryptoServiceProvider>-Objekt, um den <xref:System.Security.Cryptography.RijndaelManaged>-Schlüssel zu entschlüsseln.   
  
5. Sie verwendet ein <xref:System.Security.Cryptography.CryptoStream>-Objekt, um den Verschlüsselungsverfahrenstext-Abschnitt des <xref:System.IO.FileStream>-Verschlüsselungspakets als Byteblöcke in das <xref:System.IO.FileStream>-Objekt für die verschlüsselte Datei einzulesen und zu entschlüsseln. Nach Beendigung dieses Vorgangs ist die Entschlüsselung abgeschlossen.  
  
 Fügen Sie folgenden Code als `Click`-Ereignishandler für die Schaltfläche `Decrypt File` hinzu.  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 Fügen Sie dem Form-Objekt die folgende `DecryptFile`-Methode hinzu.  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a>Exportieren eines öffentlichen Schlüssels  
 In dieser Aufgabe wird der über die Schaltfläche `Create Keys` erstellte Schlüssel in einer Datei gespeichert. Es werden nur die öffentlichen Parameter exportiert.  
  
 In dieser Aufgabe wird das Szenario simuliert, in dem Alice ihren öffentlichen Schlüssel Bob gibt, sodass er Dateien an sie verschlüsseln kann. Er und andere, die im Besitz dieses öffentlichen Schlüssels sind, können die Dateien nicht entschlüsseln, da sie nicht das vollständige Schlüsselpaar mit privaten Parametern haben.  
  
 Fügen Sie folgenden Code als `Click`-Ereignishandler für die `Export Public Key`-Schaltfläche hinzu (`buttonExportPublicKey_Click`).  
  
 [!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
 [!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a>Importieren eines öffentlichen Schlüssels  
 In dieser Aufgabe wird der Schlüssel mit ausschließlich öffentlichen Parametern, wie er über die Schaltfläche `Export Public Key` erstellt wurde, geladen und als Schlüsselcontainername festgelegt.  
  
 In dieser Aufgabe wird das Szenario simuliert, in dem Bob den Schlüssel von Alice mit ausschließlich öffentlichen Parametern lädt, sodass er Dateien an sie verschlüsseln kann.  
  
 Fügen Sie folgenden Code als `Click`-Ereignishandler für die `Import Public Key`-Schaltfläche hinzu (`buttonImportPublicKey_Click`).  
  
 [!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
 [!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a>Abrufen eines privaten Schlüssels  
 In dieser Aufgabe wird der Schlüsselcontainername auf den Namen des Schlüssels festgelegt, der über die Schaltfläche `Create Keys` erstellt wurde. Der Schlüsselcontainer enthält das komplette Schlüsselpaar mit privaten Parametern.  
  
 In dieser Aufgabe wird das Szenario simuliert, in dem Alice ihren privaten Schlüssel dazu verwendet, Dateien zu entschlüsseln, die von Bob verschlüsselt wurden.  
  
 Fügen Sie folgenden Code als `Click`-Ereignishandler für die `Get Private Key`-Schaltfläche hinzu (`buttonGetPrivateKey_Click`).  
  
 [!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
 [!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Nachdem Sie die Anwendung erstellt haben, führen Sie die folgenden Testszenarien aus.  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a>So erstellen Sie Schlüssel, so ver- und entschlüsseln Sie  
  
1. Klicken Sie auf die Schaltfläche `Create Keys`. Die Bezeichnung zeigt den Schlüsselnamen an und zeigt, dass es sich um ein vollständiges Schlüsselpaar handelt.  
  
2. Klicken Sie auf die Schaltfläche `Export Public Key`. Durch das Exportieren der öffentlichen Schlüsselparameter wird der aktuelle Schlüssel nicht ändert.  
  
3. Klicken Sie auf die Schaltfläche `Encrypt File`, und wählen Sie eine Datei aus.  
  
4. Klicken Sie auf die Schaltfläche `Decrypt File`, und wählen Sie die soeben verschlüsselte Datei aus.  
  
5. Sehen Sie sich die nun entschlüsselte Datei an.  
  
6. Schließen Sie die Anwendung, und starten Sie sie neu, um das Abrufen von beibehaltenen Schlüsselcontainern im nächsten Szenario zu testen.  
  
#### <a name="to-encrypt-using-the-public-key"></a>So verschlüsseln Sie mit dem öffentlichen Schlüssel  
  
1. Klicken Sie auf die Schaltfläche `Import Public Key`. Die Bezeichnung zeigt den Schlüsselnamen an und zeigt, dass dies nur der öffentliche Schlüssel ist.  
  
2. Klicken Sie auf die Schaltfläche `Encrypt File`, und wählen Sie eine Datei aus.  
  
3. Klicken Sie auf die Schaltfläche `Decrypt File`, und wählen Sie die soeben verschlüsselte Datei aus. Dieser Schritt schlägt fehl, weil Sie für das Entschlüsseln den privaten Schlüssel haben müssen.  
  
 Dieses Szenario veranschaulicht, wie mit ausschließlich dem öffentlichen Schlüssel eine Datei für eine andere Person verschlüsselt wird. Normalerweise würde diese Person Ihnen nur den öffentlichen Schlüssel geben und den privaten Schlüssel für Entschlüsselung zurückbehalten.  
  
#### <a name="to-decrypt-using-the-private-key"></a>So entschlüsseln Sie mit dem privaten Schlüssel  
  
1. Klicken Sie auf die Schaltfläche `Get Private Key`. Die Bezeichnung zeigt den Schlüsselnamen an und zeigt, ob es sich um das vollständige Schlüsselpaar handelt.  
  
2. Klicken Sie auf die Schaltfläche `Decrypt File`, und wählen Sie die soeben verschlüsselte Datei aus. Dies ist erfolgreich, weil Sie das vollständige Schlüsselpaar zum Entschlüsseln haben.  
  
## <a name="see-also"></a>Siehe auch

- [Kryptografiedienste](cryptographic-services.md)
