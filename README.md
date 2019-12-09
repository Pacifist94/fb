
<html>
<head>
	<title></title>
	<link href="jquery-ui.css" rel="stylesheet">
	<style> 

	</style>
</head>
<body>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>

<textarea id="txt" rows="15" cols="15">There is some text here.</textarea>
<input type="button" id="btn" value="OK" />

<!-- Menu -->

<ul style="width:100px;" id="menu">
	<li><div>Item 1</div></li>
	<li><div>Item 2</div></li>
	<li><div>Item 3</div></li>
	<li><div>Item 4</div></li>
	<li><div>Item 5</div>
		<ul style="width:100px;">
			<li><div>Item 3-1</div></li>
			<li><div>Item 3-2</div></li>
			<li><div>Item 3-3</div>
	<ul style="width:100px;">
			<li><div>Item 3-1</div></li>
			<li><div>Item 3-2</div></li>
			<li><div>Item 3-3</div></li>
			<li><div>Item 3-4</div></li>
			<li><div>Item 3-5</div></li>
		</ul>
			</li>
			<li><div>Item 3-4</div></li>
			<li><div>Item 3-5</div></li>
		</ul>
	</li>
	<li><div>Item 4</div></li>
	<li><div>Item 5</div></li>
</ul>


<script src="external/jquery/jquery.js"></script>
<script src="jquery-ui.js"></script>

<script >
	$( "#menu" ).menu();



function checkcarret(){
	   var $txt = jQuery("#txt");
        var caretPos = $txt[0].selectionStart;
alert(caretPos);
}


/*insert text at cursor pos */
function inserter() {
		var $txt = jQuery("#txt");
        var caretPos = $txt[0].selectionStart;
        var textAreaTxt = $txt.val();
        var txtToAdd = "\nPLACE_HOLDER\n";
        $txt.val(textAreaTxt.substring(0, caretPos) + txtToAdd + textAreaTxt.substring(caretPos) );


}

/*--------------*/
jQuery("#btn").on('click', function() {
        var $txt = jQuery("#txt");
        var caretPos = $txt[0].selectionStart;
        var textAreaTxt = $txt.val();
        var txtToAdd = "HELLO";
        $txt.val(textAreaTxt.substring(0, caretPos) + txtToAdd + textAreaTxt.substring(caretPos) );
    });
/*---------*/


$(document).on('keydown', function ( e ) {
    // You may replace `c` with whatever key you want
    if ((e.metaKey || e.altKey) && ( String.fromCharCode(e.which).toLowerCase() === 'q') ) {
        console.log( "You pressed alt + q" );
        inserter();
    }
});
</script>

</body>
</html>
