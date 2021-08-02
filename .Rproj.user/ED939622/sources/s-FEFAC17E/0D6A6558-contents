library(shiny)

#Fields to save from the form

fields <- c("date", "technician", "note")


#Shiny app to record preventative maintenance

ui <- fluidPage(
  titlePanel("Preventative Maintenance Log"),
 
 "Instructions: Choose Weekly or Monthly Log and record your Name and any Notes",
   
  selectInput(inputId = "technician",
              label = "Biorepository Technician",
              choices =c("Jennifer Ness","Amanda Moors", "Debra Ellisor", "Jennifer Hoguet"),
              selected = NULL,
              width = 200), 
  date(),
 
  textInput(inputId = "note",
           label = "Note",
           width = 500),
  
  numericInput(inputId = "dlevel",
               label = "Dipstick Level",
               value = 5, min = 0, max = 10),

  
  plotOutput(outputId = "hist"))

server <- function(input, output) {
  
  output$hist <- renderPlot({
    hist(rnorm(input$dlevel))
  })
  
  
}

shinyApp(ui, server)