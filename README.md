# AxisVM SAF Export (beta)

AxisVM papildinājums, kas atvērto modeli eksportē **SAF 2.2.0** failā (Structural Analysis Format, `.xlsx`). Tas nelieto AxisVM SAF moduli: modelis tiek nolasīts caur AxisVM COM saskarni. SAF failu var ievest [KFORMA](https://design.kforma.lv) 3D FEM modulī («SAF imports») un citās programmās, kas lasa SAF.

*An AxisVM add-on that exports the open model to a **SAF 2.2.0** file (Structural Analysis Format, `.xlsx`). It does not use the AxisVM SAF module: the model is read through the AxisVM COM interface. The SAF file can be imported into the [KFORMA](https://design.kforma.lv) 3D FEM module ("SAF import") and other programs that read SAF.*

## Lejupielāde / Download

**[AxisVMSafExport.msi](https://github.com/Inovskis/axisvm-saf-exporter/releases/latest/download/AxisVMSafExport.msi)** — jaunākā versija / latest version ([visas versijas / all versions](https://github.com/Inovskis/axisvm-saf-exporter/releases))

## Prasības / Requirements

- Windows x64, AxisVM X8 (64 bitu).
- AxisVM licencē jābūt **COM modulim**: bez tā spraudņa poga ir pelēka.
  *The AxisVM licence must include the **COM module**; without it the plugin button is greyed out.*

## Instalēšana / Installation

1. Aizveriet AxisVM un palaidiet `AxisVMSafExport.msi` (vajag administratora tiesības).
   *Close AxisVM and run `AxisVMSafExport.msi` (administrator rights needed).*
2. Windows var rādīt «Windows protected your PC» (instalētājs vēl nav parakstīts): **More info → Run anyway**.
   *Windows may show "Windows protected your PC" (the installer is not signed yet): **More info → Run anyway**.*
3. Instalētājs atrod AxisVM mapi, ieliek spraudni `<AxisVM>\Plugins\SAF\` un ar AxisVM skriptiem reģistrē COM serveri un .NET spraudņu ielādētāju. Komandrindas rīks `axisvm-saf.exe` — `Program Files\AxisVM SAF Export\`.
   *The installer finds the AxisVM folder, puts the plugin in `<AxisVM>\Plugins\SAF\` and registers the COM server and .NET plugin loader with AxisVM's own scripts. The command line tool `axisvm-saf.exe` goes to `Program Files\AxisVM SAF Export\`.*

Bez jautājumiem / silent: `msiexec /i AxisVMSafExport.msi /qn`. Noņemšana / removal: *Settings → Apps*.

## Lietošana / Usage

AxisVM rīkjoslā *Geometry* beigās poga **SAF** vai izvēlne **Plugins → SAF → SAF export**. Blakus SAF failam tiek saglabāts `*_SAF.log.txt` ar brīdinājumiem — tajā ir viss, ko SAF nevar attēlot.

*The **SAF** button at the end of the *Geometry* toolbar, or **Plugins → SAF → SAF export**. Next to the SAF file a `*_SAF.log.txt` is saved with warnings — everything SAF cannot represent is listed there.*

Komandrinda / command line: `axisvm-saf "C:\models\project.axs" project_SAF.xlsx`

## Beta

Eksportē mezglus, stieņus, šķērsgriezumus, virsmas ar atvērumiem, balstus (arī elastīgus), šarnīrus, stingos ķermeņus un saišu elementus, slodžu gadījumus, kombinācijas un galvenos slodžu tipus. Pārbaudiet rezultātu pret AxisVM (mezglu un elementu skaits, reakciju summas) un ziņojiet par kļūdām [Issues](https://github.com/Inovskis/axisvm-saf-exporter/issues).

*Exports nodes, members, cross-sections, surfaces with openings, supports (including flexible), hinges, rigid bodies and link elements, load cases, combinations and the main load types. Check the result against AxisVM (node and element counts, reaction sums) and report problems under [Issues](https://github.com/Inovskis/axisvm-saf-exporter/issues).*

Neatkarīgs rīks, nav saistīts ar AxisVM izstrādātāju. AxisVM ir Inter-CAD Kft. preču zīme.
*Independent tool, not affiliated with the AxisVM developer. AxisVM is a trademark of Inter-CAD Kft.*
