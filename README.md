- 👋 Hi, I’m @RusselQA
public class Main {

    public static void main(String[] args) {

        // a TileGrid represents a 2D grid composed of Tiles
        TileGrid tileGrid = SwingApplications.startTileGrid(
                AppConfig.newBuilder()
                        // The number of tiles horizontally, and vertically
                        .withSize(60, 30)
                        // You can choose from a wide array of CP437, True Type or Graphical tilesets
                        // that are built into Zircon
                        .withDefaultTileset(CP437TilesetResources.rexPaint16x16())
                        .build());

        // A Screen is an abstraction that lets you use text GUI Components
        // You can have multiple Screens attached to the same TileGrid to be able to create multiple
        // screens for your app.
        Screen screen = Screen.create(tileGrid);

        // Creating text GUI Components is super simple
        Label label = Components.label()
                .withText("Hello, Zircon!")
                .withAlignment(ComponentAlignments.alignmentWithin(tileGrid, ComponentAlignment.CENTER))
                .build();

        // Screens can hold GUI components
        screen.addComponent(label);

        // Displaying a screen will make it visible. It will also hide a previously shown Screen.
        screen.display();

        // Zircon comes with a plethora of built-in color themes
        screen.setTheme(ColorThemes.arc());
    }
}
