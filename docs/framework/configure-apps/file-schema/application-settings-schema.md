---
title: Schema für Anwendungseinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f11be59941759687806591feb1edcce28b2119e6
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48780965"
---
# <a name="application-settings-schema"></a><span data-ttu-id="7f337-102">Schema für Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="7f337-102">Application Settings schema</span></span>

<span data-ttu-id="7f337-103">Anwendungseinstellungen ermöglichen eine Windows Forms- oder ASP.NET-ANWENDUNGEN-Anwendung zum Speichern und Abrufen von anwendungsspezifische und benutzerspezifische Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="7f337-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="7f337-104">In diesem Kontext ein *Einstellung* ist Information, die speziell auf die Anwendung oder für den aktuellen Benutzer spezifisch sein können – alles aus einer Datenbank-Verbindungszeichenfolge, die dem Benutzer die Standardfenstergröße bevorzugte.</span><span class="sxs-lookup"><span data-stu-id="7f337-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="7f337-105">Einstellungen für Anwendungen in einer Windows Forms-Anwendung verwendet standardmäßig die <xref:System.Configuration.LocalFileSettingsProvider> -Klasse, die das Konfigurationssystem .NET verwendet wird, um die Einstellungen in eine XML-Konfigurationsdatei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7f337-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="7f337-106">Weitere Informationen zu den Dateien, die von den Einstellungen für Anwendungen verwendet, finden Sie unter [Architektur der Anwendungseinstellungen](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="7f337-106">For more information about the files used by application settings, see [Application Settings Architecture](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="7f337-107">Die Anwendungseinstellungen definiert die folgenden Elemente als Teil der verwendeten Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="7f337-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="7f337-108">Element</span><span class="sxs-lookup"><span data-stu-id="7f337-108">Element</span></span>                    | <span data-ttu-id="7f337-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f337-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="7f337-110">**\<"ApplicationSettings" >**</span><span class="sxs-lookup"><span data-stu-id="7f337-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="7f337-111">Enthält alle  **\<Einstellung >** Tags, die spezifisch für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7f337-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="7f337-112">**\<UserSettings >**</span><span class="sxs-lookup"><span data-stu-id="7f337-112">**\<userSettings>**</span></span>        | <span data-ttu-id="7f337-113">Enthält alle  **\<Einstellung >** Tags, die spezifisch für den aktuellen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7f337-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="7f337-114">**\<Festlegen von >**</span><span class="sxs-lookup"><span data-stu-id="7f337-114">**\<setting>**</span></span>             | <span data-ttu-id="7f337-115">Definiert eine Einstellung.</span><span class="sxs-lookup"><span data-stu-id="7f337-115">Defines a setting.</span></span> <span data-ttu-id="7f337-116">Untergeordnetes Element des  **\<"ApplicationSettings" >** oder  **\<UserSettings >**.</span><span class="sxs-lookup"><span data-stu-id="7f337-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="7f337-117">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="7f337-117">**\<value>**</span></span>               | <span data-ttu-id="7f337-118">Der Wert einer Einstellung wird definiert.</span><span class="sxs-lookup"><span data-stu-id="7f337-118">Defines a setting's value.</span></span> <span data-ttu-id="7f337-119">Untergeordnetes Element des  **\<Einstellung >**.</span><span class="sxs-lookup"><span data-stu-id="7f337-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="7f337-120">\<"ApplicationSettings" >-Element</span><span class="sxs-lookup"><span data-stu-id="7f337-120">\<applicationSettings> element</span></span>

<span data-ttu-id="7f337-121">Dieses Element enthält alle  **\<Einstellung >** Tags, die für eine Instanz der Anwendung auf einem Clientcomputer spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="7f337-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="7f337-122">Es definiert keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="7f337-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="7f337-123">\<UserSettings >-Element</span><span class="sxs-lookup"><span data-stu-id="7f337-123">\<userSettings> element</span></span>

<span data-ttu-id="7f337-124">Dieses Element enthält alle  **\<Einstellung >** Tags, die für den Benutzer spezifisch sind, die die Anwendung derzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="7f337-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="7f337-125">Es definiert keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="7f337-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="7f337-126">\<Festlegen von >-Element</span><span class="sxs-lookup"><span data-stu-id="7f337-126">\<setting> element</span></span>

<span data-ttu-id="7f337-127">Dieses Element definiert eine Einstellung an.</span><span class="sxs-lookup"><span data-stu-id="7f337-127">This element defines a setting.</span></span> <span data-ttu-id="7f337-128">Es hat die folgenden Attribute.</span><span class="sxs-lookup"><span data-stu-id="7f337-128">It has the following attributes.</span></span>

| <span data-ttu-id="7f337-129">Attribut</span><span class="sxs-lookup"><span data-stu-id="7f337-129">Attribute</span></span>        | <span data-ttu-id="7f337-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f337-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="7f337-131">**name**</span><span class="sxs-lookup"><span data-stu-id="7f337-131">**name**</span></span>         | <span data-ttu-id="7f337-132">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7f337-132">Required.</span></span> <span data-ttu-id="7f337-133">Die eindeutige ID der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="7f337-133">The unique ID of the setting.</span></span> <span data-ttu-id="7f337-134">Einstellungen, die mit Visual Studio erstellt wurden, werden mit dem Namen gespeichert `ProjectName.Properties.Settings`.</span><span class="sxs-lookup"><span data-stu-id="7f337-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="7f337-135">**serializedAs**</span><span class="sxs-lookup"><span data-stu-id="7f337-135">**serializedAs**</span></span> | <span data-ttu-id="7f337-136">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7f337-136">Required.</span></span> <span data-ttu-id="7f337-137">Das Format für den Wert in Text zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="7f337-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="7f337-138">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="7f337-138">Valid values are:</span></span><br><br><span data-ttu-id="7f337-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="7f337-139">- `string`.</span></span> <span data-ttu-id="7f337-140">Der Wert wird als Zeichenfolge serialisiert eine <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="7f337-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="7f337-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="7f337-141">- `xml`.</span></span> <span data-ttu-id="7f337-142">Der Wert wird mit XML-Serialisierung serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7f337-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="7f337-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="7f337-143">- `binary`.</span></span> <span data-ttu-id="7f337-144">Der Wert wird als Text codiert-binär mit binärer Serialisierung serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7f337-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="7f337-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="7f337-145">- `custom`.</span></span> <span data-ttu-id="7f337-146">Der Einstellungsanbieter inhärenten Kenntnisse über diese Einstellung hat und serialisiert und deserialisiert es.</span><span class="sxs-lookup"><span data-stu-id="7f337-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="7f337-147">\<Wert >-Element</span><span class="sxs-lookup"><span data-stu-id="7f337-147">\<value> element</span></span>

<span data-ttu-id="7f337-148">Dieses Element enthält den Wert einer Einstellung an.</span><span class="sxs-lookup"><span data-stu-id="7f337-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="7f337-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7f337-149">Example</span></span>

<span data-ttu-id="7f337-150">Das folgende Beispiel zeigt eine Datei mit den Anwendungseinstellungen, die zwei Einstellungen mit Anwendungsbereich und zwei benutzerspezifische Einstellungen definiert:</span><span class="sxs-lookup"><span data-stu-id="7f337-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7f337-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f337-151">See also</span></span>

<span data-ttu-id="7f337-152">[Übersicht über Anwendungseinstellungen](~/docs/framework/winforms/advanced/application-settings-overview.md) </span><span class="sxs-lookup"><span data-stu-id="7f337-152">[Application Settings Overview](~/docs/framework/winforms/advanced/application-settings-overview.md) </span></span>  
[<span data-ttu-id="7f337-153">Architektur der Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="7f337-153">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)
