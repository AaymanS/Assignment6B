-----------------------------------------------------------------------------------------
-- Created by: Aayman Shameem
-- Created on: Apr 25, 2018
--
-- This code will calculate pi with the user's input
-----------------------------------------------------------------------------------------

-- asking for the input
local titleText = display.newText( "Input the number of repeats below", display.contentCenterX, display.contentCenterY - 675, native.systemFont, 150 )

-- the input box
local inputBox = native.newTextField( display.contentCenterX, display.contentCenterY - 177, 720, 277 )

-- the answer when it shows up
local answerText = display.newText( "Answer", display.contentCenterX, display.contentCenterY + 430, native.systemFont, 177 )

-- the ENTER button
local button = display.newImageRect( "./assets/sprites/enterButton.png", 675, 277 )
button.x = display.contentCenterX
button.y = display.contentCenterY + 177
button.id = "Le button of repeats"

local function theReapeatButton( event )

	local sum = 0

	-- make sure the input is actually a number
	local realInput = tonumber( inputBox.text )

	-- checking for negative inputs
	if realInput < 0 then
		answerText.text = "INVALID INPUT!!!"
	end

	-- make sure for weird things
	if realInput == nil then
		answerText.text = "ENTER A PROPER NUMBER!!!"
	end


	if realInput > 0 then

		for i=0, realInput do
			sum = sum + ( (-1)^(i)) / (2 * (i) + 1 )
		end

		sum = sum * 4

		answerText.text = sum
	end



end 

button:addEventListener( "touch", theReapeatButton )
