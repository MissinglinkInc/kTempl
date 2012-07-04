kTempl template engine
by Keiya Chinen <keiya_21@yahoo.co.jp>

-----

テンプレートをHTMLのscriptブロックとして書きます
===============================================

テンプレートはこんなかんじで。

	<script type='text/x-ktempl' id='templ'>
		<p>{name}は{age}才です</p>
	</script>

JavaScriptはこんなかんじ
=======================

# syntax
	var tmpl1 = new KTempl({template:'templ'});
	
	var result = tmpl1.render({
		name:'僕',
		age:'1',
	});
	
	$('#result1').text(result);

# result
> &lt;p&gt;僕は1才です&lt;/p&gt;

イテレータをつかう
=================

Arrayのかたちで渡すとイテレーションされる
# syntax
	var tmpl2 = new KTempl({template:'templ'});
	
	var result2 = tmpl2.render([
		{
			name:'僕',
			age:'5',
		},
		{
			name:'あなた',
			age:'12',
		}
	]);
	
	$('#result2').html(result2);

# result
> 僕は5才です
> 
> あなたは12才です

