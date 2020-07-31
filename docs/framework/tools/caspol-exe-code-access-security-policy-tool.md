---
title: Caspol.exe (Richtlinientool für die Codezugriffssicherheit)
description: Überblick zu Caspol.exe, dem Richtlinientool für die Codezugriffssicherheit (Code Access Security, CAS). Dieses Tool ermöglicht Benutzern und Administratoren, die Sicherheitsrichtlinie für verschiedene Richtlinienebenen zu ändern.
ms.date: 03/30/2017
helpviewer_keywords:
- permission sets, modifying security policy
- security policy [.NET Framework], Code Access Security Policy tool
- enterprise security policy
- referencing code groups and permission sets
- user security policy
- Caspol.exe
- Code Access Security Policy tool
- code groups, modifying security policy
- application development [.NET Framework], security
- machine security policy
- security policy [.NET Framework], modifying
- manually editing security configuration files
ms.assetid: d2bf6123-7b0c-4e60-87ad-a39a1c3eb2e0
ms.openlocfilehash: 4d29c22c09e42be5596d860d90b182e512ad3b45
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167328"
---
# <a name="caspolexe-code-access-security-policy-tool"></a>Caspol.exe (Richtlinientool für die Codezugriffssicherheit)
Das Sicherheitsrichtlinientool für den Codezugriff (Caspol.exe) ermöglicht es Benutzern und Administratoren, die Sicherheitsrichtlinien für die Richtlinienebene des Computers, des Benutzers und des Unternehmens zu ändern.  
  
> [!IMPORTANT]
> Ab .NET Framework 4 wirkt sich Caspol.exe nur dann auf CAS-Richtlinien (Code Access Security, Codezugriffssicherheit) aus, wenn das [\<legacyCasPolicy>-Element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) auf `true` festgelegt ist. Alle von CasPol.exe angezeigten oder geänderten Einstellungen gelten nur für Anwendungen, die die Verwendung der CAS-Richtlinie abonnieren. Weitere Informationen finden Sie unter [Sicherheitsänderungen](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).  
  
> [!NOTE]
> 64-Bit-Computer enthalten 64-Bit- und 32-Bit-Versionen der Sicherheitsrichtlinie. Um sicherzustellen, dass die Richtlinienänderungen sowohl für 32-Bit- als auch für 64-Bit-Anwendungen gelten, führen Sie die 32- und die 64-Bit-Version von Caspol.exe aus.  
  
 Das Sicherheitsrichtlinientool für den Codezugriff wird automatisch mit Visual Studio und .NET Framework installiert. Sie finden Caspol.exe auf 32-Bit-Systemen in %windir%\Microsoft.NET\Framework\\*Version* bzw. in %windir%\Microsoft.NET\Framework64\\*Version* auf 64-Bit-Systemen. (Zum Beispiel ist %windir%\Microsoft.NET\Framework64\v4.030319\caspol.exe der Speicherort für .NET Framework 4 auf einem 64-Bit-System.) Wenn auf Ihrem Computer mehrere .NET Framework-Versionen parallel ausgeführt werden, sind unter Umständen mehrere Versionen des Tools installiert. Sie können das Tool aus dem Installationsverzeichnis heraus ausführen. Es empfiehlt sich jedoch, die [Eingabeaufforderungen](developer-command-prompt-for-vs.md) zu verwenden, da Sie dann nicht zum Installationsordner navigieren müssen.  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```console
caspol [options]  
```  
  
## <a name="parameters"></a>Parameter  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**-addfulltrust** *assembly_file*<br /><br /> oder<br /><br /> **-af** *assembly_file*|Fügt eine Assembly, die ein benutzerdefiniertes Sicherheitsobjekt implementiert, z. B. eine benutzerdefinierte Berechtigung oder Mitgliedschaftsbedingung, zur Liste der vollständig vertrauenswürdigen Assemblys einer bestimmten Richtlinienebene hinzu. Das Argument *assembly_file* gibt die hinzuzufügende Assembly an. Diese Datei muss mit einem [starken Namen](../../standard/assembly/strong-named.md) signiert werden. Sie können eine Assembly mit dem [Strong Name-Tool (Sn.exe)](sn-exe-strong-name-tool.md) mit einem starken Namen signieren.<br /><br /> Wenn ein Berechtigungssatz, der eine benutzerdefinierte Berechtigung enthält, einer Richtlinie hinzugefügt wird, muss außerdem die Assembly, die diese Berechtigung implementiert, zur Liste der vollständig vertrauenswürdigen Assemblys dieser Richtlinienebene hinzugefügt werden. Assemblys, die benutzerdefinierte Sicherheitsobjekte implementieren, z. B. benutzerdefinierte Codegruppen oder Mitgliedschaftsbedingungen, die in Sicherheitsrichtlinien wie der Computerrichtlinie angewendet werden, sollten generell zur Liste der vollständig vertrauenswürdigen Assemblys hinzugefügt werden. **Achtung:** Wenn die Assembly, die das benutzerdefinierte Sicherheitsobjekt implementiert, auf andere Assemblys verweist, müssen Sie zur Liste der vollständig vertrauenswürdigen Assemblys zunächst die Assemblys hinzufügen, auf die verwiesen wird. Benutzerdefinierte Sicherheitsobjekte, die mit Visual Basic, C++ und JScript erstellt wurden, verweisen entweder auf Microsoft.VisualBasic.dll, Microsoft.VisualC.dll oder Microsoft.JScript.dll. In der Standardeinstellung befinden sich diese Assemblys nicht in der Liste der vollständig vertrauenswürdigen Assemblys. Sie müssen die entsprechende Assembly zur Liste der vollständig vertrauenswürdigen Assemblys hinzufügen, bevor Sie ein benutzerdefiniertes Sicherheitsobjekt hinzufügen. Wenn Sie dies unterlassen, wird das Sicherheitssystem beschädigt, und sämtliche Assemblys können nicht mehr geladen werden. In diesem Fall wird die Sicherheit nicht durch die Option **-all -reset** von Caspol.exe repariert. Zum Wiederherstellen der Sicherheit müssen Sie die Sicherheitsdateien manuell bearbeiten und das benutzerdefinierte Sicherheitsobjekt entfernen.|  
|**-addgroup** {*parent_label &#124; parent_name*} *mship pset_name* [*flags*]<br /><br /> oder<br /><br /> **-ag** {*parent_label &#124; parent_name*} *mship pset_name* [*flags*]|Fügt der Hierarchie der Codegruppen eine neue Codegruppe hinzu. Es kann entweder *parent_label* oder *parent_name* angegeben werden. Das Argument *parent_label* gibt die Bezeichnung der Codegruppe an (z.B. 1 oder 1.1), die der hinzuzufügenden Codegruppe übergeordnet ist. Das Argument *parent_name* gibt den Namen der Codegruppe an, die der hinzuzufügenden Codegruppe übergeordnet ist. Da sich *parent_label* und *parent_name* synonym verwenden lassen, müssen sie von Caspol.exe unterschieden werden können. Aus diesem Grund darf *parent_name* nicht mit einer Zahl beginnen. Außerdem kann *parent_name* nur die Zeichen A-Z, 0-9 und den Unterstrich enthalten.<br /><br /> Das Argument *mship* gibt die Mitgliedschaftsbedingung für die neue Codegruppe an. Weitere Informationen zu *mship*-Argumenten finden Sie in der Tabelle weiter unten in diesem Abschnitt.<br /><br /> Das Argument *pset_name* stellt den Namen des Berechtigungssatzes dar, der der neuen Codegruppe zugeordnet wird. Darüber hinaus können ein oder mehrere *Flags* für die neue Gruppe festgelegt werden. Weitere Informationen zu *flags*-Argumenten finden Sie in der Tabelle weiter unten in diesem Abschnitt.|  
|**-addpset** {*psfile* &#124; *psfile* p*set_name*}<br /><br /> oder<br /><br /> **-ap** {*named*_*psfile* &#124; *psfile* *pset_name*}|Fügt einer Richtlinie einen neuen benannten Berechtigungssatz hinzu. Der Berechtigungssatz muss in XML verfasst und als XML-Datei gespeichert sein. Wenn die XML-Datei den Namen des Berechtigungssatzes enthält, wird nur diese Datei (*psfile*) angegeben. Enthält die XML-Datei den Namen des Berechtigungssatzes nicht, müssen sowohl der Name der XML-Datei (*psfile*) als auch der Name des Berechtigungssatzes (*pset_name*) angegeben werden.<br /><br /> Beachten Sie, dass alle in einem Berechtigungssatz verwendeten Berechtigungen in Assemblys definiert sein müssen, die im globalen Assemblycache enthalten sind.|  
|**-a**[**ll**]|Gibt an, dass alle folgenden Optionen für die Computer-, Benutzer- und Unternehmensrichtlinie gelten. Die Option **-all** bezieht sich immer auf die Richtlinie des aktuell angemeldeten Benutzers. Verwenden Sie die Option **-customall**, um auf die Benutzerrichtlinie eines anderen Benutzers zu verweisen.|  
|**-chggroup** {*label &#124;name*} {*mship* &#124; *pset_name* &#124;<br /><br /> *flags* `}`<br /><br /> oder<br /><br /> **-cg** {*label &#124;name*} {*mship* &#124; *pset_name* &#124;<br /><br /> *flags* `}`|Ändert bei einer Codegruppe die Mitgliedschaftsbedingung, den Berechtigungssatz oder die Festlegung für das **exclusive**-Flag, das **levelfinal**-Flag, das **name**-Flag oder das **description**-Flag. Sie können entweder *label* oder *name* festlegen. Das Argument *label* gibt die Bezeichnung der Codegruppe an (z.B. 1 oder 1.1). Durch das Argument *name* wird der Name der zu ändernden Codegruppe festgelegt. Da sich *label* und *name* synonym verwenden lassen, müssen sie von Caspol.exe unterschieden werden können. Aus diesem Grund darf *name* nicht mit einer Zahl beginnen. Außerdem kann *name* nur die Zeichen A-Z, 0-9 und den Unterstrich enthalten.<br /><br /> Mit dem Argument *pset_name* wird der Name des der neuen Codegruppe zuzuordnenden Berechtigungssatzes angegeben. Informationen zu *mship*-Argumenten und *flags*-Argumenten finden Sie in den Tabellen weiter unten in diesem Abschnitt.|  
|**-chgpset**  *psfile pset_name*<br /><br /> oder<br /><br /> **-cp** *psfile pset_name*|Ändert einen benannten Berechtigungssatz. Das Argument *psfile* liefert die neue Definition des Berechtigungssatzes. Dabei handelt es sich um eine serialisierte Berechtigungssatzdatei im XML-Format. Das Argument *pset_name* stellt den Namen des zu ändernden Berechtigungssatzes dar.|  
|**-customall**  *path*<br /><br /> oder<br /><br /> **-ca**  *path*|Gibt an, dass alle folgenden Optionen für die Computer- und Organisationsrichtlinie sowie die benutzerdefinierte Benutzerrichtlinie gelten. Der Speicherort für die benutzerdefinierte Sicherheitskonfigurationsdatei des Benutzers muss mit dem *path*-Argument angegeben werden.|  
|**-cu**[**stomuser**] *path*|Ermöglicht die Verwaltung einer benutzerdefinierten Benutzerrichtlinie, die nicht für den Benutzer gilt, für den Caspol.exe gerade ausgeführt wird. Der Speicherort für die benutzerdefinierte Sicherheitskonfigurationsdatei des Benutzers muss mit dem *path*-Argument angegeben werden.|  
|**-enterprise**<br /><br /> oder<br /><br /> **-en**|Gibt an, dass alle folgenden Optionen für die Richtlinie auf Organisationsebene gelten. Benutzer, die keine Administratoren der Organisation sind, verfügen nicht über ausreichende Rechte zum Ändern der Unternehmensrichtlinie. Sie können sich diese allerdings anzeigen lassen. In Szenarien, die sich nicht auf die Organisation beziehen, werden die Computer- und die Benutzerrichtlinie von dieser Richtlinie standardmäßig nicht beeinflusst.|  
|**-e**[**xecution**] {**on** &#124; **off**}|Aktiviert oder deaktiviert den Mechanismus, der die Berechtigung zum Ausführen vor dem Beginn der Codeausführung überprüft. **Hinweis**:  Dieser Schalter wurde in .NET Framework 4 und höheren Versionen entfernt. Weitere Informationen finden Sie unter [Sicherheitsänderungen](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).|  
|**-f**[**orce**]|Unterdrückt den Test auf Selbstzerstörung des Tools und ändert die Richtlinie entsprechend den Benutzerangaben. In der Regel überprüft Caspol.exe, ob eine Richtlinienänderung die Ausführungsfähigkeit von Caspol.exe selbst beeinträchtigt. Trifft dies zu, speichert Caspol.exe die Richtlinienänderung nicht und gibt eine Fehlermeldung aus. Um zu erzwingen, dass die Richtlinie von Caspol.exe geändert wird, auch wenn dadurch die Ausführung von Caspol.exe nicht mehr möglich ist, wird die Option **-force** verwendet.|  
|**-h**[**elp**]|Zeigt die Befehlssyntax und Optionen für Caspol.exe an.|  
|**-l**[**ist**]|Listet die Hierarchie der Codegruppen sowie die Berechtigungssätze für den angegebenen Computer, Benutzer oder die Organisation bzw. für alle Richtlinienebenen auf. Caspol.exe zeigt zuerst die Bezeichnung der Codegruppe an und dann deren Namen, sofern vorhanden.|  
|**-listdescription**<br /><br /> oder<br /><br /> **-ld**|Listet alle Codegruppenbeschreibungen für die angegebene Richtlinienebene auf.|  
|**-listfulltrust**<br /><br /> oder<br /><br /> **-lf**|Zeigt den Inhalt der Liste der vollständig vertrauenswürdigen Assemblys für die angegebene Richtlinienebene an.|  
|**-listgroups**<br /><br /> oder<br /><br /> **-lg**|Zeigt die Codegruppen der angegebenen bzw. aller Richtlinienebenen an. Caspol.exe zeigt zuerst die Bezeichnung der Codegruppe an und dann deren Namen, sofern vorhanden.|  
|**-listpset** oder **-lp**|Zeigt die Berechtigungssätze für die angegebene bzw. alle Richtlinienebenen an.|  
|**-m**[**achine**]|Gibt an, dass alle folgenden Optionen für die Richtlinie auf Computerebene gelten. Benutzer, die keine Administratoren sind, verfügen nicht über ausreichende Rechte zum Ändern der Computerrichtlinie. Sie können sich diese allerdings anzeigen lassen. Für Administratoren ist **-machine** die Standardeinstellung.|  
|**-polchgprompt** {**on** &#124; **off**}<br /><br /> oder<br /><br /> **-pp** {**on** &#124; **off**}|Aktiviert oder deaktiviert die Eingabeaufforderung, die immer dann angezeigt wird, wenn Caspol.exe ausgeführt wird und die verwendete Option Richtlinienänderungen bewirkt.|  
|**-quiet**<br /><br /> oder<br /><br /> **-q**|Deaktiviert vorübergehend die Eingabeaufforderung, die normalerweise für eine Option angezeigt wird, die Richtlinienänderungen bewirkt. Die Einstellung für die Eingabeaufforderung für globale Änderungen wird nicht verändert. Verwenden Sie die Option nur für einen einzelnen Befehl, um zu verhindern, dass die Eingabeaufforderung für alle Caspol.exe-Befehle deaktiviert wird.|  
|**-r**[**ecover**]|Stellt Richtlinien aus einer Sicherungsdatei wieder her. Bei jeder Änderung einer Richtlinie speichert Caspol.exe die alte Version in einer Sicherungsdatei.|  
|**-remfulltrust** *assembly_file*<br /><br /> oder<br /><br /> **-rf**  *assembly_file*|Entfernt eine Assembly aus der Liste der vollständig vertrauenswürdigen Assemblys einer Richtlinienebene. Diese Operation sollte ausgeführt werden, wenn ein Berechtigungssatz, der eine benutzerdefinierte Berechtigung enthält, von einer Richtlinie nicht mehr verwendet wird. Sie sollten eine Assembly, die eine benutzerdefinierte Berechtigung implementiert, jedoch nur dann aus der Liste der vollständig vertrauenswürdigen Assemblys entfernen, wenn die Assembly keine weiteren verwendeten benutzerdefinierten Berechtigungen implementiert. Wenn eine Assembly aus der Liste entfernt wird, sollten darüber hinaus alle Assemblys entfernt werden, die von dieser abhängen.|  
|**-remgroup** {*label &#124;name*}<br /><br /> oder<br /><br /> **-rg** {l*abel &#124; name*}|Entfernt die mit ihrer Bezeichnung bzw. dem Namen angegebene Codegruppe. Wenn die angegebene Codegruppe untergeordnete Codegruppen aufweist, werden diese von Caspol.exe entfernt.|  
|**-rempset** *pset_name*<br /><br /> oder<br /><br /> **-rp** *pset_name*|Entfernt den angegebenen Berechtigungssatz aus der Richtlinie. Das Argument *pset_name* gibt den zu entfernenden Berechtigungssatz an. Caspol.exe entfernt den Berechtigungssatz nur dann, wenn er keiner Codegruppe zugeordnet ist. Die (integrierten) Standardberechtigungssätze können nicht entfernt werden.|  
|**-reset**<br /><br /> oder<br /><br /> **-rs**|Setzt Richtlinien auf ihren Standardzustand zurück und speichert sie auf dem Datenträger. Dies empfiehlt sich, wenn eine geänderte Richtlinie irreparabel beschädigt ist und Sie erneut mit den installierten Standardeinstellungen beginnen möchten. Das Zurücksetzen bietet sich auch dann an, wenn die Standardrichtlinie als Ausgangspunkt für Änderungen an bestimmten Sicherheitskonfigurationsdateien verwendet werden soll. Weitere Informationen finden Sie unter [Manuelles Bearbeiten der Sicherheitskonfigurationsdateien](#cpgrfcodeaccesssecuritypolicyutilitycaspolexeanchor1).|  
|**-resetlockdown**<br /><br /> oder<br /><br /> **-rsld**|Setzt Richtlinien auf eine restriktivere Version des Standardzustands zurück und speichert sie auf dem Datenträger. Erstellt eine Sicherungskopie der vorherigen Computerrichtlinie und speichert sie in der Datei `security.config.bac`.  Die überschriebene Richtlinie entspricht bis auf eine Ausnahme der Standardrichtlinie: Code der Zonen `Local Intranet`, `Trusted Sites` und `Internet` wird keine Berechtigungen gewährt, und die entsprechenden Codegruppen weisen keine untergeordneten Codegruppen auf.|  
|**-resolvegroup** *assembly_file*<br /><br /> oder<br /><br /> **-rsg** *assembly_file*|Zeigt die Codegruppen an, zu denen eine bestimmte Assembly (*assembly_file*) gehört. Diese Option zeigt standardmäßig die Computer-, Benutzer- und Organisationsrichtlinienebenen an, denen die Assembly angehört. Um nur eine Richtlinienebene anzuzeigen, verwenden Sie diese Option mit einer der Optionen **-machine**, **-user** oder **-enterprise**.|  
|**-resolveperm** *assembly_file*<br /><br /> oder<br /><br /> **-rsp** *assembly_file*|Zeigt alle Berechtigungen an, die der Assembly auf der angegebenen bzw. der Standardebene der Sicherheitsrichtlinie erteilt werden, wenn die Assembly ausgeführt werden darf. Das Argument *assembly_file* gibt die Assembly an. Wenn die Option **-all** angegeben wird, berechnet Caspol.exe die Berechtigungen für die Assembly anhand der Benutzer-, Computer- und Unternehmensrichtlinie, andernfalls gelten die Standardverhaltensregeln.|  
|**-s**[**ecurity**] {**on** &#124; **off**}|Aktiviert oder deaktiviert die Codezugriffssicherheit. Durch Festlegen der Option **-s off** wird die rollenbasierte Sicherheit nicht deaktiviert. **Hinweis**:  Dieser Schalter wurde in .NET Framework 4 und höheren Versionen entfernt. Weitere Informationen finden Sie unter [Sicherheitsänderungen](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes). **Vorsicht**:  Wenn die Codezugriffssicherheit deaktiviert ist, werden alle Codezugriffsforderungen erfolgreich ausgeführt. Das Deaktivieren der Codezugriffssicherheit macht das System anfällig gegenüber Angriffen von böswilligem Code wie Viren und Würmern. Das Deaktivieren der Sicherheit führt zu einem gewissen Leistungsanstieg, sollte jedoch nur vorgenommen werden, wenn andere Sicherheitsmaßnahmen ergriffen wurden, um eine Verletzung der allgemeinen Systemsicherheit auszuschließen. Beispiele für solche Sicherheitsmaßnahmen sind u. a. das Trennen von Verbindungen mit öffentlichen Netzwerken und die physikalische Sicherung von Computern.|  
|**-u**[**ser**]|Gibt an, dass alle folgenden Optionen für die Benutzerebenenrichtlinie des Benutzers gelten, für den Caspol.exe ausgeführt wird. Für Benutzer, die keine Administratoren sind, ist **-user** die Standardeinstellung.|  
|**-?**|Zeigt die Befehlssyntax und Optionen für Caspol.exe an.|  
  
 Das Argument *mship*, das die Mitgliedschaftsbedingung für eine Codegruppe angibt, kann mit der Option **-addgroup** und der Option **-chggroup** verwendet werden. Jedes *mship*-Argument wird als .NET Framework-Klasse implementiert. *mship* wird mit einem der folgenden Argumente angegeben:  
  
|Argument|BESCHREIBUNG|  
|--------------|-----------------|  
|**-allcode**|Gibt den gesamten Code an. Weitere Informationen zu dieser Mitgliedschaftsbedingung finden Sie unter <xref:System.Security.Policy.AllMembershipCondition?displayProperty=nameWithType>.|  
|**-appdir**|Gibt das Anwendungsverzeichnis an. Wenn Sie **-appdir** als Mitgliedschaftsbedingung angeben, wird der URL-Beweis des Codes mit dem Anwendungsverzeichnisbeweis dieses Codes verglichen. Wenn die Beweiswerte identisch sind, ist die Mitgliedschaftsbedingung erfüllt. Weitere Informationen zu dieser Mitgliedschaftsbedingung finden Sie unter <xref:System.Security.Policy.ApplicationDirectoryMembershipCondition?displayProperty=nameWithType>.|  
|**-custom** *xmlfile*|Fügt eine benutzerdefinierte Mitgliedschaftsbedingung hinzu. Das obligatorische *xmlfile*-Argument gibt die XML-Datei an, die die XML-Serialisierung der benutzerdefinierten Mitgliedschaftsbedingung enthält.|  
|**-hash** *hashAlg* { **-hex** *hashValue* &#124; **-file** *assembly_file* }|Gibt Code an, der über den angegebenen Assemblyhash verfügt. Um einen Hash als Codegruppen-Mitgliedschaftsbedingung verwenden zu können, muss entweder der Hashwert oder die Assemblydatei angegeben werden. Weitere Informationen zu dieser Mitgliedschaftsbedingung finden Sie unter <xref:System.Security.Policy.HashMembershipCondition?displayProperty=nameWithType>.|  
|**-pub** { **-cert** *cert_file_name* &#124;<br /><br /> **-file** *signed_file_name* &#124; **-hex** *hex_string* }|Gibt Code an, der über den angegebenen Softwareherausgeber verfügt. Dieser wird anhand einer Zertifikatsdatei, der Signatur einer Datei oder der hexadezimalen Darstellung eines X509-Zertifikats bestimmt. Weitere Informationen zu dieser Mitgliedschaftsbedingung finden Sie unter <xref:System.Security.Policy.PublisherMembershipCondition?displayProperty=nameWithType>.|  
|**-site** *website*|Gibt Code an, der über die entsprechende Ursprungssite verfügt. Zum Beispiel:<br /><br /> `-site** www.proseware.com`<br /><br /> Weitere Informationen zu dieser Mitgliedschaftsbedingung finden Sie unter <xref:System.Security.Policy.SiteMembershipCondition?displayProperty=nameWithType>.|  
|**-strong -file** *file_name* {*name* &#124; **-noname**} {*version* &#124; **-noversion**}|Gibt Code mit einem spezifischen starken Namen an, wie er vom Dateinamen, dem Assemblynamen als Zeichenfolge und der Assemblyversion im Format *major*.*minor*.*build*.*revision* bestimmt wird. Zum Beispiel:<br /><br /> **-strong -file** myAssembly.exe myAssembly 1.2.3.4<br /><br /> Weitere Informationen zu dieser Mitgliedschaftsbedingung finden Sie unter <xref:System.Security.Policy.StrongNameMembershipCondition?displayProperty=nameWithType>.|  
|**-url** *URL*|Gibt Code an, der von der angegebenen URL stammt. Die URL muss ein Protokoll wie `http://` oder`ftp://` enthalten. Außerdem kann ein Platzhalterzeichen (\*) verwendet werden, um mehrere Assemblys von einer bestimmten URL anzugeben. **Hinweis:** Da eine URL anhand mehrerer Namen gekennzeichnet werden kann, kann durch Verwenden einer URL als Mitgliedschaftsbedingung die Identität von Code nicht sicher festgestellt werden. Verwenden Sie nach Möglichkeit Mitgliedschaftsbedingungen mit einem starken Namen, Herausgebermitgliedschaftsbedingungen oder Hashmitgliedschaftsbedingungen. <br /><br /> Weitere Informationen zu dieser Mitgliedschaftsbedingung finden Sie unter <xref:System.Security.Policy.UrlMembershipCondition?displayProperty=nameWithType>.|  
|**-zone** *zonename*|Gibt Code mit der angegebenen Ursprungszone an. Das Argument *zonename* kann einen der folgenden Werte aufweisen: **MyComputer**, **Intranet**, **Trusted**, **Internet** oder **Untrusted**. Weitere Informationen zu dieser Mitgliedschaftsbedingung finden Sie unter <xref:System.Security.Policy.ZoneMembershipCondition>-Klasse.|  
  
 Das Argument *flags*, das mit der Option **-addgroup** und der Option **-chggroup** verwendet werden kann, wird wie folgt angegeben:  
  
|Argument|BESCHREIBUNG|  
|--------------|-----------------|  
|**-description** „*Beschreibung*“|Gibt bei Verwendung mit der Option **-addgroup** die Beschreibung für eine hinzuzufügende Codegruppe an. Gibt bei Verwendung mit der Option **-chggroup** die Beschreibung für eine zu bearbeitende Codegruppe an. Das Argument *description* muss in doppelte Anführungszeichen eingeschlossen sein.|  
|**-exclusive** {**on**&#124;**off**}|**on** gibt an, dass lediglich der Berechtigungssatz berücksichtigt wird, der der hinzuzufügenden bzw. zu ändernden Codegruppe zugeordnet ist, wenn ein Code die Mitgliedschaftsbedingung der Codegruppe erfüllt. Wenn für diese Option **off** festgelegt ist, berücksichtigt Caspol.exe die Berechtigungssätze aller auf der Richtlinienebene übereinstimmenden Codegruppen.|  
|**-levelfinal** {**on**&#124;**off**}|**on** gibt an, dass keine Richtlinienebene unterhalb der Ebene der hinzugefügten bzw. geänderten Codegruppe berücksichtigt wird. In der Regel wird diese Option auf Ebene der Computerrichtlinie verwendet. Wenn dieses Flag z. B. auf Computerebene für eine Codegruppe festgelegt wird und ein Code die Mitgliedschaftsbedingung dieser Codegruppe erfüllt, wird die Benutzerebenenrichtlinie für diesen Code von Caspol.exe nicht berechnet oder auf diesen angewendet.|  
|**-name** „*Name*“|Gibt bei Verwendung mit der Option **-addgroup** den Skriptnamen für eine hinzuzufügende Codegruppe an. Gibt bei Verwendung mit der Option **-chggroup** den Skriptnamen für eine zu bearbeitende Codegruppe an. Das *name*-Argument muss in doppelten Anführungszeichen stehen. Das Argument *name* darf nicht mit einer Zahl beginnen und kann nur die Zeichen A-Z, 0-9 und den Unterstrich enthalten. Bei einem Verweis auf Codegruppen kann dieser *Name* anstelle ihrer numerischen Bezeichnung verwendet werden. *name* empfiehlt sich besonders für Scripting-Zwecke.|  
  
## <a name="remarks"></a>Hinweise  
 Die Sicherheitsrichtlinie teilt sich in drei Richtlinienebenen auf: Computerrichtlinie, Benutzerrichtlinie und Organisationsrichtlinie. Der Satz von Berechtigungen, den eine Assembly erhält, wird von der Schnittmenge der auf diesen drei Richtlinienebenen zulässigen Berechtigungssätze bestimmt. Jede Richtlinienebene wird durch eine hierarchische Codegruppenstruktur dargestellt. Jede Codegruppe verfügt über eine Mitgliedschaftsbedingung, die bestimmt, welcher Code ein Element dieser Gruppe darstellt. Außerdem wird jeder Codegruppe ein benannter Berechtigungssatz zugeordnet. Dieser Berechtigungssatz gibt die Berechtigungen an, die dem Code, der die Mitgliedschaftsbedingung erfüllt, von der Laufzeit erteilt werden. Jede Ebene der Sicherheitsrichtlinie wird von einer Hierarchie der Codegruppen und dem zugehörigen benannten Berechtigungssatz definiert und verwaltet. Die Ebene der Sicherheitsrichtlinie wird mit den Optionen **-user**, **-customuser**, **-machine** und **-enterprise** festgelegt.  
  
 Weitere Informationen zu Sicherheitsrichtlinien und die Bestimmung der Berechtigungszuteilung an Codes durch die Laufzeit finden Sie unter [Sicherheitsrichtlinienverwaltung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c1k0eed6(v=vs.100)).  
  
## <a name="referencing-code-groups-and-permission-sets"></a>Verweise auf Codegruppen und Berechtigungssätze  
 Für das vereinfachte Erstellen von Verweisen auf Codegruppen in einer Hierarchie wird mit der Option **-list** eine Liste mit Einzügen angezeigt. In dieser sind die Codegruppen und deren numerische Bezeichnungen (1, 1.1, 1.1.1 usw.) aufgeführt. Die anderen Befehlszeilenoperationen bzgl. Codegruppen verwenden für Verweise auf bestimmte Codegruppen ebenfalls die numerischen Bezeichnungen.  
  
 Bei Verweisen auf benannte Berechtigungssätze wird der entsprechende Name verwendet. Die Option **-list** zeigt eine Liste der Codegruppen an, der eine Liste der in dieser Richtlinie verfügbaren, benannten Berechtigungssätze folgt.  
  
## <a name="caspolexe-behavior"></a>Verhalten von Caspol.exe  
 Alle Optionen außer **-s**[**ecurity**] {**on** &#124; **off**} verwenden die Version von .NET Framework, mit der Caspol.exe installiert wurde. Wenn eine Version von Caspol.exe ausgeführt wird, die mit der Laufzeitversion *X* installiert wurde, gelten die Änderungen nur für diese Version. Andere eventuell vorhandene Parallelinstallationen der Laufzeit sind davon nicht betroffen. Wenn Sie Caspol.exe über die Befehlszeile ausführen und sich nicht in einem Verzeichnis für eine bestimmte Laufzeitversion befinden, erfolgt die Ausführung des Tools vom ersten Laufzeitversionsverzeichnis im Pfad aus. Dieses ist i. d. R. das Verzeichnis der zuletzt installierten Laufzeitversion.  
  
 Die Option **-s**[**ecurity**] {**on** &#124; **off**} ist eine computerweite Operation. Durch das Deaktivieren der Codezugriffssicherheit werden die Sicherheitsüberprüfungen für sämtlichen verwalteten Code und alle Benutzer des Computers beendet. Wenn mehrere Versionen von .NET Framework parallel installiert sind, deaktivieren Sie mit diesem Befehl die Sicherheit für alle auf dem Computer installierten Versionen der Laufzeit. Obgleich die Option **-list** anzeigt, dass die Sicherheit deaktiviert ist, haben die anderen Benutzer keine klaren Anzeichen dafür, dass die Sicherheit deaktiviert wurde.  
  
 Führen Benutzer ohne Administratorrechte Caspol.exe aus, beziehen sich alle Optionen auf die Richtlinie der Benutzerebene, es sei denn, die Option **-machine** wurde angegeben. Führt ein Administrator Caspol.exe aus, beziehen sich alle Optionen auf die Computerrichtlinie, es sei denn, die Option **-user** wurde angegeben.  
  
 Damit Caspol.exe ausgeführt werden kann, müssen Berechtigungen erteilt sein, die dem Berechtigungssatz **Alles** entsprechen. Das Tool verfügt über einen Schutzmechanismus. Dieser verhindert, dass Richtlinien dahingehend geändert werden, dass Caspol.exe nicht mehr die für seine Ausführung erforderlichen Berechtigungen erhält. Beim Versuch einer solchen Änderung informiert Caspol.exe Sie darüber, dass die beabsichtigte Richtlinienänderung das Tool außer Funktion setzen würde, und die Richtlinienänderung wird verweigert. Dieser Schutzmechanismus kann für einen bestimmten Befehl mithilfe der Option **-force** deaktiviert werden.  
  
<a name="cpgrfcodeaccesssecuritypolicyutilitycaspolexeanchor1"></a>
## <a name="manually-editing-the-security-configuration-files"></a>Manuelles Bearbeiten der Sicherheitskonfigurationsdateien  
 Zu den drei von Caspol.exe unterstützten Richtlinienebenen gehören drei Sicherheitskonfigurationsdateien: eine für die Computerrichtlinie, eine weitere für die Benutzerrichtlinie eines bestimmten Benutzers und eine für die Organisationsrichtlinie. Diese Dateien werden nur auf Datenträgern erstellt, wenn die Computer-, Benutzer- oder Organisationsrichtlinie mit Caspol.exe geändert wurde. Mit der Option **-reset** in Caspol.exe speichern Sie bei Bedarf die Standardsicherheitsrichtlinie auf einem Datenträger.  
  
 In den meisten Fällen ist davon abzuraten, die Sicherheitskonfigurationsdateien manuell zu bearbeiten. Allerdings kann es Szenarien geben, in denen die Änderung dieser Dateien notwendig ist, z. B. wenn ein Administrator die Sicherheitskonfiguration für einen bestimmten Benutzer bearbeiten möchte.  
  
## <a name="examples"></a>Beispiele  
 **-addfulltrust**  
  
 Angenommen, ein Berechtigungssatz wurde mit einer benutzerdefinierten Berechtigung der Computerrichtlinie hinzugefügt. Diese benutzerdefinierte Berechtigung ist in `MyPerm.exe` implementiert. `MyPerm.exe` verweist wiederum auf Klassen in `MyOther.exe`. Beide Assemblys müssen der vollständig vertrauenswürdigen Assemblyliste hinzugefügt werden. Mit dem folgenden Befehl wird die `MyPerm.exe`-Assembly der Liste der vollständig vertrauenswürdigen Assemblys für die Computerrichtlinie hinzugefügt.  
  
```console  
caspol -machine -addfulltrust MyPerm.exe  
```  
  
 Mit dem folgenden Befehl wird die `MyOther.exe`-Assembly der Liste der vollständig vertrauenswürdigen Assemblys für die Computerrichtlinie hinzugefügt.  
  
```console  
caspol -machine -addfulltrust MyOther.exe  
```  
  
 **-addgroup**  
  
 Der folgende Befehl fügt dem Stamm der Codegruppenhierarchie für die Computerrichtlinie eine untergeordnete Codegruppe hinzu. Die neue Codegruppe ist ein Element der Zone **Internet** und wird dem Berechtigungssatz **Ausführung** zugeordnet.  
  
```console  
caspol -machine -addgroup 1.  -zone Internet Execution  
```  
  
 Durch den folgenden Befehl wird eine untergeordnete Codegruppe hinzugefügt, die der Freigabe „\\\netserver\netshare“ Berechtigungen für das lokale Intranet gewährt.  
  
```console  
caspol -machine -addgroup 1. -url \\netserver\netshare\* LocalIntranet  
```  
  
 **-addpset**  
  
 Der folgende Befehl fügt der Benutzerrichtlinie den Berechtigungssatz `Mypset` hinzu.  
  
```console  
caspol -user -addpset Mypset.xml Mypset  
```  
  
 **-chggroup**  
  
 Mit dem folgenden Befehl wird der Berechtigungssatz in der Benutzerrichtlinie der mit 1.2. bezeichneten Codegruppe in den Berechtigungssatz **Ausführung** geändert.  
  
```console  
caspol -user -chggroup 1.2. Execution  
```  
  
 Der folgende Befehl ändert die Mitgliedschaftsbedingungen in der Standardrichtlinie der Codegruppe mit der Bezeichnung 1.2.1. und ändert die Einstellungen des **exclusive**-Flags. Die Mitgliedschaftsbedingung wird mit Code definiert, der aus der Zone **Internet** stammt und dessen **exclusive**-Flag aktiviert ist.  
  
```console  
caspol -chggroup 1.2.1. -zone Internet -exclusive on  
```  
  
 **-chgpset**  
  
 Durch den folgenden Befehl wird der Berechtigungssatz mit dem Namen `Mypset` in einen anderen Berechtigungssatz geändert, der in `newpset.xml` enthalten ist. Beachten Sie, dass das Ändern von Berechtigungssätzen, die von der Codegruppenhierarchie verwendet werden, vom aktuellen Release nicht unterstützt wird.  
  
```console  
caspol -chgpset Mypset newpset.xml  
```  
  
 **-force**  
  
 Der folgende Befehl verknüpft die Stammcodegruppe der Benutzerrichtlinie (die Gruppe mit der Bezeichnung 1) mit dem benannten Berechtigungssatz **Nichts**. Dadurch wird das Ausführen von Caspol.exe verhindert.  
  
```console  
caspol -force -user -chggroup 1 Nothing  
```  
  
 **-recover**  
  
 Der folgende Befehl stellt die zuletzt gespeicherte Computerrichtlinie wieder her.  
  
```console  
caspol -machine -recover  
```  
  
 **-remgroup**  
  
 Der folgende Befehl entfernt die Codegruppe mit der Bezeichnung 1.1. Untergeordnete Codegruppen dieser Codegruppe werden ebenfalls gelöscht.  
  
```console  
caspol -remgroup 1.1.  
```  
  
 **-rempset**  
  
 Der folgende Befehl entfernt den Berechtigungssatz **Ausführung** aus der Benutzerrichtlinie.  
  
```console  
caspol -user -rempset Execution  
```  
  
 Der folgende Befehl entfernt `Mypset` auf der Ebene der Benutzerrichtlinie.  
  
```console  
caspol -rempset MyPset  
```  
  
 **-resolvegroup**  
  
 Der folgende Befehl zeigt alle Codegruppen der Computerrichtlinie an, denen `myassembly` angehört.  
  
```console  
caspol -machine -resolvegroup myassembly  
```  
  
 Der folgende Befehl zeigt alle Codegruppen der Computerrichtlinie, der Organisationsrichtlinie und der angegebenen benutzerdefinierten Benutzerrichtlinie an, denen `myassembly` angehört.  
  
```console  
caspol -customall "c:\config_test\security.config" -resolvegroup myassembly  
```  
  
 **-resolveperm**  
  
 Der folgende Befehl berechnet die Berechtigungen für `testassembly` anhand der Ebene der Computer- und der Benutzerrichtlinie.  
  
```console  
caspol -all -resolveperm testassembly  
```  
  
## <a name="see-also"></a>Siehe auch

- [Extras](index.md)
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
