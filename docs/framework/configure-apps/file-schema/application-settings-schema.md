---
title: Schema für Anwendungseinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 89a08434332b0242fe57e9dcaa3b3ebcc5692d06
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927763"
---
# <a name="application-settings-schema"></a><span data-ttu-id="c31d2-102">Schema für Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="c31d2-102">Application Settings schema</span></span>

<span data-ttu-id="c31d2-103">Anwendungseinstellungen ermöglichen es einer Windows Forms-oder ASP.NET-Anwendung, anwendungsspezifische und benutzerspezifische Einstellungen zu speichern und abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c31d2-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="c31d2-104">In diesem Kontext ist eine *Einstellung* ein beliebiges Informationselement, das spezifisch für die Anwendung oder spezifisch für den aktuellen Benutzer ist – alles von einer Datenbank-Verbindungs Zeichenfolge bis zur bevorzugten Standardfenster Größe des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="c31d2-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="c31d2-105">Standardmäßig verwenden Anwendungseinstellungen in einer Windows Forms Anwendung die <xref:System.Configuration.LocalFileSettingsProvider> -Klasse, die das .NET-Konfigurationssystem zum Speichern von Einstellungen in einer XML-Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="c31d2-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="c31d2-106">Weitere Informationen zu den von Anwendungseinstellungen verwendeten Dateien finden Sie unter [Architektur der Anwendungseinstellungen](../../winforms/advanced/application-settings-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="c31d2-106">For more information about the files used by application settings, see [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="c31d2-107">Anwendungseinstellungen definiert die folgenden Elemente als Teil der Konfigurationsdateien, die Sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="c31d2-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="c31d2-108">Element</span><span class="sxs-lookup"><span data-stu-id="c31d2-108">Element</span></span>                    | <span data-ttu-id="c31d2-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c31d2-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="c31d2-110">**\<applicationSettings>**</span><span class="sxs-lookup"><span data-stu-id="c31d2-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="c31d2-111">Enthält alle  **\<Einstellungs >** Tags, die für die Anwendung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="c31d2-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="c31d2-112">**\<userSettings>**</span><span class="sxs-lookup"><span data-stu-id="c31d2-112">**\<userSettings>**</span></span>        | <span data-ttu-id="c31d2-113">Enthält alle  **\<Einstellungs >** Tags, die für den aktuellen Benutzer spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="c31d2-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="c31d2-114">**\<setting>**</span><span class="sxs-lookup"><span data-stu-id="c31d2-114">**\<setting>**</span></span>             | <span data-ttu-id="c31d2-115">Definiert eine Einstellung.</span><span class="sxs-lookup"><span data-stu-id="c31d2-115">Defines a setting.</span></span> <span data-ttu-id="c31d2-116">Untergeordnetes Element von  **\<applicationSettings >** oder  **\<User Settings >** .</span><span class="sxs-lookup"><span data-stu-id="c31d2-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="c31d2-117">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="c31d2-117">**\<value>**</span></span>               | <span data-ttu-id="c31d2-118">Definiert den Wert einer Einstellung.</span><span class="sxs-lookup"><span data-stu-id="c31d2-118">Defines a setting's value.</span></span> <span data-ttu-id="c31d2-119">Untergeordnetes Element von  **\<Setting >** .</span><span class="sxs-lookup"><span data-stu-id="c31d2-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="c31d2-120">\<applicationSettings-> Element</span><span class="sxs-lookup"><span data-stu-id="c31d2-120">\<applicationSettings> element</span></span>

<span data-ttu-id="c31d2-121">Dieses Element enthält alle  **\<Einstellungs >** Tags, die für eine Instanz der Anwendung auf einem Client Computer spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="c31d2-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="c31d2-122">Es definiert keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="c31d2-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="c31d2-123">\<userSettings-> Element</span><span class="sxs-lookup"><span data-stu-id="c31d2-123">\<userSettings> element</span></span>

<span data-ttu-id="c31d2-124">Dieses Element enthält alle  **\<Einstellungs >** Tags, die für den Benutzer spezifisch sind, der derzeit die Anwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c31d2-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="c31d2-125">Es definiert keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="c31d2-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="c31d2-126">\<festlegen > Elements</span><span class="sxs-lookup"><span data-stu-id="c31d2-126">\<setting> element</span></span>

<span data-ttu-id="c31d2-127">Dieses Element definiert eine Einstellung.</span><span class="sxs-lookup"><span data-stu-id="c31d2-127">This element defines a setting.</span></span> <span data-ttu-id="c31d2-128">Es verfügt über die folgenden Attribute:</span><span class="sxs-lookup"><span data-stu-id="c31d2-128">It has the following attributes.</span></span>

| <span data-ttu-id="c31d2-129">Attribut</span><span class="sxs-lookup"><span data-stu-id="c31d2-129">Attribute</span></span>        | <span data-ttu-id="c31d2-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c31d2-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="c31d2-131">**name**</span><span class="sxs-lookup"><span data-stu-id="c31d2-131">**name**</span></span>         | <span data-ttu-id="c31d2-132">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c31d2-132">Required.</span></span> <span data-ttu-id="c31d2-133">Die eindeutige ID der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="c31d2-133">The unique ID of the setting.</span></span> <span data-ttu-id="c31d2-134">Einstellungen, die über Visual Studio erstellt wurden, werden `ProjectName.Properties.Settings`mit dem Namen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c31d2-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="c31d2-135">**serializedAs**</span><span class="sxs-lookup"><span data-stu-id="c31d2-135">**serializedAs**</span></span> | <span data-ttu-id="c31d2-136">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c31d2-136">Required.</span></span> <span data-ttu-id="c31d2-137">Das Format, das zum Serialisieren des Werts in Text verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c31d2-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="c31d2-138">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c31d2-138">Valid values are:</span></span><br><br><span data-ttu-id="c31d2-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="c31d2-139">- `string`.</span></span> <span data-ttu-id="c31d2-140">Der Wert wird als Zeichenfolge mit einem <xref:System.ComponentModel.TypeConverter>serialisiert.</span><span class="sxs-lookup"><span data-stu-id="c31d2-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="c31d2-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="c31d2-141">- `xml`.</span></span> <span data-ttu-id="c31d2-142">Der Wert wird mithilfe der XML-Serialisierung serialisiert.</span><span class="sxs-lookup"><span data-stu-id="c31d2-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="c31d2-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="c31d2-143">- `binary`.</span></span> <span data-ttu-id="c31d2-144">Der Wert wird als Text codierte Binärdatei mit binärer Serialisierung serialisiert.</span><span class="sxs-lookup"><span data-stu-id="c31d2-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="c31d2-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="c31d2-145">- `custom`.</span></span> <span data-ttu-id="c31d2-146">Der Einstellungs Anbieter kennt diese Einstellung und serialisiert und deserialisiert Sie.</span><span class="sxs-lookup"><span data-stu-id="c31d2-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="c31d2-147">\<Wert >-Element</span><span class="sxs-lookup"><span data-stu-id="c31d2-147">\<value> element</span></span>

<span data-ttu-id="c31d2-148">Dieses Element enthält den Wert einer Einstellung.</span><span class="sxs-lookup"><span data-stu-id="c31d2-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="c31d2-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c31d2-149">Example</span></span>

<span data-ttu-id="c31d2-150">Das folgende Beispiel zeigt eine Anwendungs Einstellungsdatei, die zwei Einstellungen für Anwendungsbereiche und zwei benutzerspezifische Einstellungen definiert:</span><span class="sxs-lookup"><span data-stu-id="c31d2-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="c31d2-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c31d2-151">See also</span></span>

- [<span data-ttu-id="c31d2-152">Übersicht über Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="c31d2-152">Application Settings Overview</span></span>](../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="c31d2-153">Architektur der Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="c31d2-153">Application Settings Architecture</span></span>](../../winforms/advanced/application-settings-architecture.md)
