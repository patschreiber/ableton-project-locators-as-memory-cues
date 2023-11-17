# ableton-project-locators-as-memory-cues
Outline of how I'd probably make a Locator to Memory Cue VST. This could be useful for blocking out projects in Ableton and having Rekordbox have the memory cues already in its database.


## 1. Convert `.als` to `.xml`
```
gzip -cd MySong.als > MySong.xml
```

## 2. Extract the `Locator` data

Find the locator data in the `.xml` file and extract those.
```xml
<Locators>
			<Locators>
				<Locator Id="0">
					<LomId Value="0" />
					<Time Value="0" />
					<Name Value="1" />
					<Annotation Value="" />
					<IsSongStart Value="false" />
				</Locator>
				<Locator Id="1">
					<LomId Value="0" />
					<Time Value="64" />
					<Name Value=" " />
					<Annotation Value="" />
					<IsSongStart Value="false" />
				</Locator>
				<Locator Id="2">
					<LomId Value="0" />
					<Time Value="20" />
					<Name Value="2" />
					<Annotation Value="" />
					<IsSongStart Value="false" />
				</Locator>
			</Locators>
		</Locators>
```

## 3. Massage the `Locator` data 

 Conver the locator points in a memory cue-digestible format. This is probably where things get a little iffy, undoubtably caused by Rekordbox's proprietary format.
 


## Appendix: Problems

1. The `master.db` Rekordbox file seems to be proprietary and difficult to open, so it's hard to see how the memory cue data is constructed.
2. Further, writing to the protected db may be a blocker. 
